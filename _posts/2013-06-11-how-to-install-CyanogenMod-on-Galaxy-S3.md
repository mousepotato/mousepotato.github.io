---
layout: post
title: "How to install CyanogenMod on Galaxy S3"
description: "CyanogenMod是Android上一个开源的固件（ROM）管理和定制软件。玩转Andorid ROM必备。本文介绍在Galaxy S3如何安装CyanogenMod"
category: "Technique"
tags:
- Android
---
{% include JB/setup %}

----------------

Galaxy S3 安装CyanogenMod

CyanogenMod是Android上一个开源的固件（ROM）管理和定制软件。玩转Andorid ROM必备。下面介绍如何在Galaxy S3上安装CyanogenMod。

### 1. 下载 CyanogenMod
通过这个[链接 http://get.cm/?device=i9300](http://get.cm/?device=i9300)下载，分为三个版本：    

- nightly (最新版，小白鼠专用)  
- test  （测试版本，较稳定）  
- stable  （稳定版本）  

可以根据自己喜好选择。

### 2. 安装 CyanogenMod

将下载好的.zip文件放到S3手机上。有两种方法：    

-  直接将手机连接电脑上传    
-  将手机连接电脑通过adb上传  
> ./adb push ~/Downloads/cm-10.1-20130610-NIGHTLY-i9300.zip /sdcard/0/cmupdater