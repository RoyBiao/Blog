---
title: android错误积累
date: 2016-12-02 17:25:22
tags: android
---

### 1.使用全局变量更新适配器（待研究）
异步获取数据更新全局变量，并发送消息更新适配器，解决方法：使用局部变量。
```
     java.lang.IllegalStateException: The content of the adapter has changed but ListView did not receive a notification. Make sure the content of your adapter is not modified from a background thread, but only from the UI thread. Make sure your adapter calls notifyDataSetChanged() when its content changes. 
```

### 2.jni内存溢出
使用jni时，如果新建的对象有返回java层，则交给java虚拟机管理内存记得释放内存，否则一定要手动释放内存 。 
jni底层内存溢出错误：local reference table overflow max 512

### 3.is your activity running？
Dialog在调用show或dismiss的时候，判断dialog所依赖的activity是否被销毁，否则将有可能发生Unable to add window -- token android.os.BinderProxy@7fd5e6 is not valid; is your activity running？的问题。
例如：异步操作中，Activity已经退出，但是异步线程还没有执行完毕，如果此时异步线程通知主线程显示Dialog，将发生Dialog找不到可以依赖的Activity。
```
if (context instanceof Activity) {
    if (((Activity) context).isFinishing()) {
        return ;
    } else {
        dialog.show() ;
    }
}
```

### 4.找不到javax.*
使用android studio找不到rt.jar下的javax.* 。解决方法：
在build.gradle添加rt.jar文件的支持
```
    provided files ('/Library/Java/JavaVirtualMachines/jdk1.8.0_45.jdk/Contents/Home/jre/lib/rt.jar')
```
不要使用compile，否则打包的时候将和android.jar 下的javax.*发生冲突。
 