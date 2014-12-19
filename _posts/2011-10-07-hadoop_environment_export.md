---
layout: post
title: "Hadoop安装过程中环境变量的配置即Ubuntu 中export命令的使用"
description: "Hadoop安装过程中环境变量的配置即Ubuntu 中export命令的使用"
category: "Technique"
tags:
- Hadoop
- Linux
- Ubuntu
---


Hadoop安装时需要指定HADOOP_HOME位置。可以使用如下三种export方法:

## 1. 直接使用export命令

		export HADOOP_HOME=/home/sj/hadoop-0.20.2
		export PATH=$HADOOP_HOME/bin:$PATH  

看是否已经设好，可用命令export查看 

		export  


![Hadoop](/assets/images/2011/10/declare.png)


**注意：** 直接用export命令只会对当前shell窗口起作用，重启或者重新打开shell窗口时，环境变量就会丢失。

## 2. 修改全局profile文件

`/etc/profile` 是一个global config file，会影响系统全局用户，如果你只想对single user生效的话，可以修改 `~/.bash_profile`

		sudo vi /etc/profile
		
添加：

		export HADOOP_HOME=/home/sj/hadoop-0.20.2 
		export PATH=$PATH:$HADOOP_HOME/bin

可以通过 

		echo $HADOOP_HOME

检查设置是否成功。

![Hadoop2](/assets/images/2011/10/echohome.png)    

**注意：** 直接修改`/etc/profile`文件需要注销系统才能够生效。且永久有效。
 
## 3.  修改`.bashrc`文件
  	 
		sudo vi ~/.bashrc


在里面加入：


		export HADOOP_HOME=/home/sj/hadoop-0.20.2 
		export PATH=$PATH:$HADOOP_HOME/bin

**注意：** 修改后必须使用 source ~/.bashrc 命令使其生效。