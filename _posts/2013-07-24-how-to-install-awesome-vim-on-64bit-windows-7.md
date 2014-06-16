--- 
layout: post
title: How to install Awesome Vim on 64bit Windows 7
description: "本文介绍如何在64位的Windows 7 操作系统上安装vim并且通过github配置各种vim插件。"
category: Technique
tags: 
- Vim
- Windows
---
{% include JB/setup %}

----------------

# How to install vim for windows

1. Download <del>[gVIM_X64](https://code.google.com/p/vim-win3264/wiki/Win64Binaries)</del> [gvim Self-installing executable](ftp://ftp.vim.org/pub/vim/pc/gvim74.exe), [msysgit](https://code.google.com/p/msysgit/downloads/list), and the [dot_vim](https://github.com/humiaozuzu/dot-vimrc ), make sure install gvim in `C:\vim\vim74` folder.

2. Download ctags and other utilities at this [link](http://s.yunio.com/viCkke) and put it in `C:\vim\vim74`.

3. Download Monaco font at this [link](http://s.yunio.com/GBKtUh).

4. Edit the the environment variable add `PATH=C:\vim\vim74;C:\Program Files\Git\cmd`. 

5. Enter command line and execute:

	> git clone git://github.com/humiaozuzu/dot-vimrc.git C:\vim\vim74  

6. change `vimrc` to `_vimrc`.
7. change the first line to `source C:\vim73\bundles.vim`.

8. `git clone https://github.com/gmarik/vundle.git C:\vim\vim74`.

9. In gVIM, run `:BundleInstall`.

10. Last important step，in the folder `C:\Users\sli` create file`_vimrc` and add the following:

		set runtimepath+=C:\vim\vim74
		
		source C:\vim\_vimrc



That's it!!
