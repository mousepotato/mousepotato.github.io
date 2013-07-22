---
layout: post
title: "Bluehost上如何安装Git"
description: "如何在bluhost的空间上安装Git"
category: Technique
tags:
- Linux
- Ubuntu
---
{% include JB/setup %}

----------------

最新版本的Git可以在[这里下载](http://code.google.com/p/git-core/)


### 安装

	mkdir src && cd src
	wget http://git-core.googlecode.com/files/git-1.7.7.1.tar.gz
	tar -zxvf git-1.7.7.1.tar.gz
	cd git-1.7.7.1
	make  && mak install

通过命令：
> git –version

测试安装是否成功。

That's it!!
