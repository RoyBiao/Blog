---
title: git安装
date: 2016-12-02 17:00:25
tags: git
---

## Windows 下使用git
1. 下载安装Git for windows
2. 安装完成之后打开Git Bash
3. 输入ssh-keygen.exe，一路回车
4. cd ~/.ssh
5. cat id_rsa.pub，将命令输出的内容发送给管理员，或者用Windows文件浏览器打开用户的我的文档，打开.ssh文件夹，将id_rsa.pub发给管理员。
6. 配置git
git config --global user.name sang.zhang    ##用户名为git的用户名，需要将用户名也一并发给管理员，此处统一为《名.姓》，如张三，用户名即为sang.zhang
git config --global user.email sang.zhang@163.com ##用户邮箱，不需要发给管理员
7. enjoy git

## Ubuntu下使用git
1. 安装git：sudo apt-get install git-core
2. 打开终端输入：ssh-keygen，一路回车
3. cd ~/.ssh
4. cat id_rsa.pub，将命令输出的内容发送给管理员，或者用文件浏览器打开用户的Home目录，打开.ssh文件夹（此为隐藏文件夹），将id_rsa.pub发给管理员。
5. 配置git
git config --global user.name sang.zhang    ##用户名为git的用户名，需要将用户名也一并发给管理员，此处统一为《名.姓》，如张三，用户名即为sang.zhang
git config --global user.email sang.zhang@163.com ##用户邮箱，不需要发给管理员
6. enjoy git

## Git 手册
http://www.nshen.net/article/2011-08-03/git-note/

