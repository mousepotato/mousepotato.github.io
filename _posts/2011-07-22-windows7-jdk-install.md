---
layout: post
title: Windows 7 64bit JDK 安装配置
tags:
- Technique
- Java
- Windows 
---
Windows 7下安装64 位JDK教程

开发Java首先要安装Java Development Kit (JDK). Windows 7 64bit下安装JDK以及配置的方法，和XP基本一样。

## 一、下载JDK相应版本

点击[此连接](http://www.oracle.com/technetwork/java/javase/downloads/jdk-6u26-download-400750.html)下载Windows x64对应的JDK文件`jdk-6u26-windows-x64`。

## 二、安装配置

一直点击下一步，进行操作，安装JDK和JRE默认会安装在`C:\Program Files\Java`

右键点击`我的电脑->属性->高级系统设置->高级->环境变量` 
 
![JDK](/assets/uploads/2011/07/image.png)

新建或者编辑变量名：`PATH`，修改其值为：

> .;C:\Program Files\Java\jdk1.6.0_26\bin;

新建或者编辑变量名：`CLASSPATH`，修改其值为：  

> C:\Program Files\Java\jdk1.6.0_26\lib;C:\Program Files\Java\jdk1.6.0_26\lib\dt.jar;C:\Program Files\Java\jdk1.6.0_26\lib\tools.jar

## 三、测试使用

打开命令行，输入：

> java –version

可以看到如下界面，表示安装成功。

![JDK2](/assets/uploads/2011/07/image1.png)
