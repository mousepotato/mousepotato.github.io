---
layout: post
title: "CTex使用"
description: "最近有折腾了下CTex以及Beamer，遇到不少问题，因为使用了最新版本，网上教程比较少，本文稍做总结"
category: "Research"
tags:
- Latex
---
{% include JB/setup %} 


最近有折腾了下CTex以及Beamer，遇到不少问题，因为使用了最新版本，网上教程比较少，总结下：

## 一、CTex安装

去 [cTex官网](http://www.ctex.org/CTeXDownload)下载最新版本的CTex，[v2.9.0.152 Full(1.08G)](ftp://ftp.ctex.org/pub/tex/systems/ctex/2.9/CTeX_2.9.0.152_Full.exe)  包含完整版 [MiKTeX](http://www.ctex.org/MiKTeX)。
建议使用ftp下载，[ftp地址](ftp://ftp.ctex.org/pub/tex/systems/ctex/2.9/CTeX_2.9.0.152_Full.exe)

![cTex1](/assets/images/2011/10/ctex1.jpg)  
![cTex2](/assets/images/2011/10/ctex2.jpg)  

安装完CTeX后，记得安装CTeX FontSetup，因为CTex可以默认支持中文。

![cTex3](/assets/images/2011/10/ctex3.jpg)


## 二、如何安装新的Beamer Theme

默认的Theme路径是：
> C:\Program Files (x86)\CTEX\MiKTeX\tex\latex\beamer\base\themes\theme  


当你添加一个新的theme到这个路径下时，需要Refresh FNDB，这样在编译.tex文件时才不会报错。
![cTex4](/assets/images/2011/10/mikoption.png)

## 三、常见错误
1、首次运行.tex文件若出现如下错误

	! Undefined control sequence.
	\trans@languagepath -&gt;\languagename
	,English
	l.54 \end{frame}


的解决方案是：<font color="#ff0000">CTeX—&gt;MiKTeX—&gt;Maintenance (Admin)—&gt;Update (Admin) 更新MiKTeX</font>


![cTex5](/assets/images/2011/10/update_mik.png)  

2、gbk2uni.exe文件无法找到

自行修改WinEdt6的配置文件。
> <font color="#ff0000">C:\Program Files (x86)\CTEX\WinEdt\Exec\ExeCompiler.edt </font>

在END前加入:  

		// add by SJ   10/26/2011  
		 IfStr("%!9","LaTeX",    "=",!"JMP(!'gbk2uni');");
		 IfStr("%!9","PDFLaTeX", "=",!"JMP(!'gbk2uni');");
		 IfStr("%!9","TeXify",   "=",!"JMP(!'gbk2uni');");
		 IfStr("%!9","PDFTeXify","=",!"JMP(!'gbk2uni');");
		 JMP(!'gbk2uni-Done');
		
		:gbk2uni:: ================================================
		
		 IfFileExists("%!6\%N.out","",!"JMP(!'gbk2uni-Done');");
		 IfStr("%$('%!9-WinEdt_Console');",'1','=',&gt;
		   !|RunConsole('gbk2uni.exe "%N"','%!6','%!9 ...',1,1);|,&gt;
		   !|WinExe('','gbk2uni.exe "%N"','%!6','%!9 ...', %!0, %!2,&gt;
		            '', '%b\_Out.log', '%b\_Err.log',%!1);|);
		
		:gbk2uni-Done:: ================================================ 

或者直接到[这里](http://www.hooklee.com/tex/gbk2uni.zip) 下载一个gbk2uni文件解压后放到 <font color="#ff0000">C:\Program Files (x86)\CTEX\MiKTeX\miktex\bin </font><font color="#333333">下就OK了。</font>

3、WinEdt 6破解

> 咳咳，下次再说。

