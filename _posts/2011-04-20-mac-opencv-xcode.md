---
layout: post
title: "Mac OS 10.6.7下安装OpenCV 2.2并使用Xcode 3.2.6进行开发教程"
description: "如何在Mac下配置Opencv2.2并且使用Xcode开发环境进行开发教程"
category: "Research"
tags:
- Mac
- OpenCV
---
{% include JB/setup %} 

如何在Mac下配置Opencv2.2并且使用Xcode开发环境进行开发教程：

## 一、OpenCV2.2的安装（使用MacPorts安装）
1、在Mac OS上安装MacPorts，然后执行

	sudo port selfupdate  
	sudo port install opencv

执行后将会安装64bit版本  
[http://opencv.willowgarage.com/wiki/Mac_OS_X_OpenCV_Port](http://opencv.willowgarage.com/wiki/Mac_OS_X_OpenCV_Port)

## 二、配置Xcode开发环境 （for Xcode 3.2.6版本）

- Create a new Xcode project using the Command Line Tool
- Select Project -&gt; Edit Project Settings  
- Select the Build tab  
- Set Configuration to All Configurations  
- In the Architectures section, double-click Valid Architectures and remove all the PPC architectures and remove i386 as well  
- In the Search Paths section set Header Search Paths to `/opt/local/include`
- Close the Project Info window
- Select Project -&gt; New Group and create a group called OpenCV Frameworks
- With the new group selected, select Project -&gt; Add to Project…
- Press the "/" key to get the Go to the folder prompt  
- Enter `/opt/local/lib` 
- Select `libopencv_core.2.2.0.dylib`, `libopencv_highgui.2.2.0.dylib`, and `libopencv_imgproc.2.2.0.dylib` (maybe more, depend on your need).
- Click Add  
- Uncheck Copy Items… and click Add


完成后的Xcode如下

    
    
## 三、编译，运行，测试

编写代码时加入：

	#include</span> "opencv/cv.h"
	#include</span> "opencv/highgui.h"

运行结果：
