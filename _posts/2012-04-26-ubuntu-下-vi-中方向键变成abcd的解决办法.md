---
layout: post
title: Ubuntu 下 VI 中方向键变成ABCD的解决办法
tags:
- Technique
- Ubuntu
---

Ubuntu 下 VI 中方向键变成ABCD的解决办法


Open `~/.vimrc` and write:		
		set nocp
		set backspace=2  
save and exit.

That's it!!