---
layout: post
title: 如何让Ubuntu 11.04启动直接进入命令行模式
tags:
- Technique
- Ubuntu
---

如何让Ubuntu 11.04启动直接进入命令行模式  

1. 打开grub

		sudo vi /etc/default/grub 

2. Change the following lines:

		GRUB_CMDLINE_LINUX_DEFAULT="quiet splash"
		GRUB_CMDLINE_LINUX_DEFAULT="text"

	to: 

		#GRUB_CMDLINE_LINUX_DEFAULT="quiet splash"
		GRUB_CMDLINE_LINUX_DEFAULT="text"

3.  update grub

		sudo update-grub

4. reboot

		sudo reboot
		
5. 要想回到图形界面： 

		startx
		

如果修改出错停留在<font color="#ff0000">checking battery state</font> 上的话，可以按`ctrl+alt+f1`调出命令行(shell prompt)
