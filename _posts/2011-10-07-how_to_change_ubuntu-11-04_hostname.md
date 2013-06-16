---
layout: post
title: 如何永久修改Ubuntu 11.04 的hostname
tags:
- Technique
- Ubuntu
---

如何永久修改Ubuntu的hostname


1. 直接 `hostname newname`。但是重启后失效。  
2. 首先修改   

		 sudo vi /etc/hostname  
 
3. 然后修改 

		sudo vi /etc/hosts 127.0.0.1 newname

4. 重启生效
