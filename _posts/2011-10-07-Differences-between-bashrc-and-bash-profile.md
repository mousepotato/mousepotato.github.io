---
layout: post
title: "~/.bashrc 与 ~/.bash_profile的区别"
description: "在使用Linux，Unix或者是Mac OS是，当碰到环境变量设置时，大家多数会接触到`~/.bashrc`与 `~/.bash_profile`两个文件。那么他们的区别到底在哪，各自用处是什么，如何使用呢？"
category: "Technique"
tags:
- Linux
- Ubuntu
---
{% include JB/setup %} 

在使用Linux，Unix或者是Mac OS是，当碰到环境变量设置时，大家多数会接触到`~/.bashrc`与 `~/.bash_profile`两个文件。那么他们的区别到底在哪，各自用处是什么，如何使用呢？

## 1 .bash_profile 与 .bashrc的区别
> `.bash_profile` is executed for login shells, while `.bashrc` is executed for interactive non-login shells.

## 2. 什么是 login 和 non-login shell？
当你使用ssh或者直接在机器内login输入用户名和密码时，`.bash_profile`就会被调用来初始化shell环境。  

但是，当你已经登陆系统，打开一个GNome或者KDE的控制台窗口的时候 `.bashrc`会被调用，并且每次在新开一个窗口时`.bashrc`还会再次被调用。

## 3. 为什么会有这两个不同的文件？
正是因为这两个文件的调用情况不同，才会同时出现。比如当你每次启动机器的时候想查看一些冗长的控制台信息的时候 （例如，负载信息，内存使用信息，当前用户等等）。因为你只想在登录的时候查看，而不是每次打开shell窗口的时候都显示。所以合理的做法是把这些调用命令放入`.bash_profile`文件。但是<p style="color: #ff0000;">注意，在Mac OS X中Terminal.app每打开一个新窗口时将会调用`.bash_profile`而不是`.bashrc`。这与其他linux和Unix恰恰相反。</p>

## 4. 如何使用这两个文件呢？

大多时候你并不想单独分开管理这两个文件。当你每次设置一个环境变量的时候，你希望他能够自动的应用到这两个文件中。这可以通过source命令实现。

每次只编辑和修改`.bashrc` 文件。这里新开的shell窗口就会应用生效。然后只需在`.bash_profile`中加入下列代码：
	
		if [ -f ~/.bashrc ]; then
		   source ~/.bashrc
		fi


这样每次登陆控制台的时候`.bashrc`文件也会自动被调用。
