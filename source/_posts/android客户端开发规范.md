---
title: android客户端开发规范
date: 2016-12-19 10:47:55
tags: android
---

### 一．编写目的
编码规范对于程序员而言尤为重要，有以下几个原因： 一个软件的生命周期中，80%的花费在于维护。几乎没有任何一个软件，在其整个生命周期中，均由最初的开发人员来维护。编码规范可以改善软件的可读性，可以让程序员尽快而彻底地理解新的代码。如果你将源码作为产品发布，就需要确任它是否被很好的打包并且清晰无误，一如你已构建的其它任何产品。
统一的编码规范可以使程序可读性增强，使程序更易于被理解，并降低维护成本。
### 二．预期读者及阅读建议
本规范文档的主要读者为Android开发团队成员。建议每位Android开发人员在进行代码编写前仔细阅读此文档，并按文档的规范要求进行编码。
保持代码的简明清晰，避免过分的编程技巧。简单是最美。保持代码的简单化是软件工程化的基本要求。不要过分追求技巧，否则会降低程序的可读性。
### 三．Android编码规范
* **命名规范**
    + **包名/类名**
        - \*.activity   ：页面用到的Activity类,例如：MainActivity.java
        - \*.model      ：程序中要用到的JavaBean类,例如：UserModel.java
        - \*.adapter    ：进行页面的数据适配的Adapter类,例如：UserAdapter.java
        - \*.info       ：程序中要用到的非JavaBean的其它信息类,例如：Constants.java
        - \*.util       ：公共工具方法类,例如：DevicesUtil.java
        - \*.db         ：数据库操作类,例如：UserDao.java
        - \*.widget     ：自定义的view等类 例如：LoadingDialog.java(功能＋控件名)
        - \*.interfaces ：所有接口,例如：OnClickListener.java
        - \*.service    ：Service服务,例如：DownService.java
        - \*.broadcast  ：Broadcast服务,例如：UserBroadcast.java
    + **变量名**
        1. 变量的命名应具有“自明性”，例如声明一个表示电话号码的局部变量，可以这么写：“String mobileNumber”。 除了for循环中可以使用int i，j这样的命名方式，其他地方禁止使用这种没有“自明性”的命名
        2.  所有静态变量都必须以s开头，例如：“sMobileNumber”
        3.  所有的非静态变量必须以m开头，例如：“mMobileNumber”
        4.  所有的局部变量只需要说明作用，  例如：“mobileNumber”
        5.  所有常量必须采用全大写方式，单词之间用下划线分割，例如：“MOBILE_NUMBER”。此时f.不要再加如“s”或“m”前缀
        6.  局部变量的作用域一定要最小化
        7.  所有成员变量必须都定义在类的开始，定义顺序如下：常量->public 变量->protected 变量->private 变量
    + **xml文件名**
        + drawable/anim/colors
            - 采用'根节点＋功能‘:selector_dialog_btn.xml
        + mipmap
            - 按钮图片使用‘btn_功能’：btn_login_normal.png
            - 背景图片使用‘bg_功能’：bg_head.png
            - 图标图片使用‘icon_功能’：icon_more_help.png
        + layout 
            - Activity布局 ：activity_login.xml
            - Fragment布局 ：fragment_mine.xml
            - Adapter布局  ： item_user.xml
            - 布局导入      ：layout_user.xml
        + menu
        + values
    + **id名**
        - TextView      －>  XXXTxt或XXXTextView
        - EditText      －>  XXXExt或XXXEditText
        - Button        －>  XXXBtn或XXXButton
        - ImageButton   －>  XXXImgBtn或XXXImageButton
        - ImageView     －>  XXXImg或XXXImageView
        - LinearLayout  －>  XXXLinear或XXXLinearLayout
        - RelativeLayout－>  XXXRelative或XXXRelativeLayout
        - FrameLayout   －>  XXXFrame或XXXFrameLayout
        - ListView      －>  XXXList或XXXListView
        - GridView      －>  XXXGrid或XXXGridView
        - RecycleView   －>  XXXRecycle或XXXRecycleView
        - ScrollView    －>  XXXScroll或XXXScrollView
        - SwipeRefreshLayout －>  XXXSwipeRefresh或XXXSwipeRefreshLayout
        以此类推其它的id的命名，对一些有歧义的应该使用控件的全名来命名;
        Java代码里控件命名方式必须和资源ID保持一致。
* **XML布局代码规范**
    + 如没有特殊情况，一律使用dp和sp单位，如果代码中需要使用，调用xml中的资源
    + 所有的颜色写在colors文件中,文字写在strings文件中。代码中除注释外不允许出现文字。