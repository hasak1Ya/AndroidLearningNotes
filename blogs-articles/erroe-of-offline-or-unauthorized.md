---
title: android真机测试之offline或unauthorized错误
date: 2016-04-23 16:30:25
categories: [android,学习笔记]
tags: [真机调试,offline]
---
在开发中，使用真机测试较为方便，然而在ide连接手机时，adb device 提示 **offline** 或者 **unauthorized**(中文：未授权的)会令大家非常困扰。<!--more-->我也同样为此而浪费了很多时间。这里，介绍一种较为方便的解决方法（亲测有效）：
先删除.android 文件夹下的adbkey文件夹,再连接数据线，让其重新授权。
对于.android 文件夹，一般在电脑c盘的用户/用户名 下，它是用于存放android虚拟机的。如果将sdk配置到了环境变量中，则.android文件夹在相应的sdk目录下。
此外，网上还有其他的方法，不过都没有解决：

 1. 用数据线连接手机，在设备管理器中把手机的驱动卸载了，然后重启，重新连接数据线；
 2. 打开手机设置，进入 开发人员选项，关闭 usb调试 ，撤销usb授权，最后重新打开；
 3. 重启adb：①在编辑器中重启或者关掉编辑器，同时在任务管理器中结束adb.exe;
 ②使用命令行：windows下，（win+R）-->cmd 进入命令行，输入一次以下命令：
                            
```
adb kill-server;
adb start-server;
```
4. 使用第三方的软件，如豌豆荚（曾经用过，可用）
总之，不同的人有不同的方法，选择一种自己可以接受的，能够有效解决问题就行。



