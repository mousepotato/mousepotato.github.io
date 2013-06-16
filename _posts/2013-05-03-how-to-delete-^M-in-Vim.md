---
layout: post
title:  How to delete ^M in vim
tags:
- Technique
- Vim
---

如何删除Vm中的多余^M

## ^M的由来
1. Vim 支持三种文件格式（dos,mac,unix）,不同的文件格式将以不同的ending characters (line terminators)结尾。

2. 三种文件格式的ending characters分别为：

		- dos: CRLF (each line ends with an LF character)
		- mac: CR only	(each line ends with two characters, CR then LF)
		- unix: LF only (each line ends with a CR character)

`LF` 是 `Line Feed`的缩写，意为换行，表示将光标移到下一行 (**move cursor down**)。注意`是将光标移到当前字符的下一行，并没有移到最左侧`。对应符号为，`Ctrl-J`或者hex的`0A`。

`CR` 是 `Carriage Return`的缩写，意为回车键，表示将光标移到最左边（**return cursor to left margin**）,注意`还是在当前行，没有开始新的一行`。 对应符号为，`Ctrl-M`，`^M`或者hex的`OD`。


3. 当你在Mac下编辑的文件文件格式为unix格式时，结尾就会显示 `^M`。
  
## Vim中如何查看文件格式相关命令
1. 查看隐藏的结尾字符：

	`:set list` 
	
	取消显示对应的是：`:set nolist`

2.  查看文件格式：

	`:set ff` 

3. 强制以某一种文件格式打开文件:
  
  	`:e ++ff=unix`，或者 `:e ++ff=dos`

4. Vim中文件格式帮助命令：

	`:h ffs`

## 如何删除
1. 去掉所有多余的^M: 

	`:%s/^M$//g `
	
	注意：命令中的^M 是通过键入`CTRL-V CTRL-M`生成的！
	
	该命令的意思是 “去掉所有行末的^M”
	
2. 处理仅有^M而没有carrage回车键的情况:
	
	`:%s/^M/ /g `
	
	注意：命令中的^M 是通过键入`CTRL-V CTRL-M`生成的！
	
	该命令的意思是 “将仅有^M而没有换行符的地方替换成换行符”。

That's it!!
