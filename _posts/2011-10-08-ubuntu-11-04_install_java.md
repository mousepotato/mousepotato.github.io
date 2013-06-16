---
layout: post
title: Ubuntu 11.04安装Java环境
tags:
- Technique
- Java
- Ubuntu
---

由于Ubuntu11.04默认安装的是open-JDK,但有的东西只支持sun-jdk.所以这里需要更换.大概如下命令: 

1. 更换数据源

		sudo add-apt-repository "deb http:/archive.canonical.com/ lucid partner" 

2. 更新数据源

		sudo apt-get update 

3. 安装sun-jdk  
		
		sudo apt-get install sun-java6-jdk sun-java6-plugin

4. 执行sudo gedit /etc/environment，添加配置
<font color="#ff0000">(/usr/lib/jvm/java-6-sun实际上是个链接指向java-6-sun-1.6.0.26文件夹)</font> 

		PATH="/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/games:/usr/lib/jvm/java-6-sun-1.6.0.26/bin”
		CLASSPATH=”. :/usr/lib/jvm/java-6-sun-1.6.0.26/lib”
		JAVA_HOME=” /usr/lib/jvm/java-6-sun-1.6.0.26/”

		sudo update-alternatives --install /usr/bin/java java /usr/lib/jvm/java-6-sun-1.6.0.26/bin/java 300
		sudo update-alternatives --install /usr/bin/javac javac /usr/lib/jvm/java-6-sun-1.6.0.26/bin/javac 300


5. 查看系统默认安装的java配置首选项，敲入数字做选择

		sudo update-alternatives --config java

6. 要使配置生效必须重启机器或者在命令行输入  

		. /etc/environment

7.  测试  

		java -version 
