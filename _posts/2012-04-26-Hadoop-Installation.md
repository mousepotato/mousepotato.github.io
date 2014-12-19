---
layout: post
title: "Ubuntu下安装Hadoop"
description: "Ubuntu下安装Hadoop教程"
category: "Technique"
tags:
- Hadoop
- Ubuntu
---



Ubuntu下安装Hadoop

### 1. Hadoop下载

	wget http://mirrors.axint.net/apache//hadoop/core/hadoop-0.20.2/hadoop-0.20.2.tar.gz

### 2. 解压
	tar –zvxf hadoop-0.20.2.tar.gz

### 3. 把Hadoop 的安装路径添加到`/etc/profile` 中
	export HADOOP_HOME=/home/sj/hadoop-0.20.2
	export PATH=$HADOOP_HOME/bin:$PATH

### 3. 配置Hadoop
see this blog: [Setup a multinode Cassandra using Ubuntu and Virtualbox](http://anotherbug.com/2012/06/05/setup-a-multinode-cassandra-using-ubuntu-12-04-and-virtualbox/)