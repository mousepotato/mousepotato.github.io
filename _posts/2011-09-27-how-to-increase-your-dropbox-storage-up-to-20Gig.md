---
layout: post
title: "如何免费将Dropbox的容量增加到20G"
description: "本文介绍如何免费将Dropbox的容量增加到20G" 
category: "Technique"
tags: 
- Ubuntu
- VirtualBox
---
{% include JB/setup %} 

如何将Dropbox的容量增加到20G  
How to increase your dropbox storage up to 20G  

Dropbox允许用户通过推荐（refer）其它用户注册的方式来增加自己的容量。很显然，如果想扩容只能不停的发送邀请。其实不用这样。可以偷懒推荐自己就可以扩容。由于Dropbox通过你注册电脑的Mac地址来唯一标识你的电脑。如果用自己的电脑不停的换邮箱推荐自己。这样肯定会失败的。但是可以通过以下方法：

## 一、使用VirtualBox安装一个虚拟机系统。

我安装了ubuntu-11.04-desktop-i386

## 二、在虚拟机里面安装dropbox，实现增容。

## 三、通过软件设置更新Mac Address

![dropbox](/assets/images/2011/09/update_macaddress.jpg)  

##四、如此反复，可以扩容至16G。使用.edu邮箱，每次refer可扩容512M。

![dropbox2](/assets/images/2011/09/referral_status.jpg)

## 五、最终结果

![dropbox3](/assets/images/2011/09/total_space.jpg)