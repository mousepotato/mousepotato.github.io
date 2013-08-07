---
layout: post
title: "Mac OS 下使用Automator批量将图片转成pdf文件"
description: "Automator是Mac OS X内建的一个应用程序，用于自动化处理很多重复的工作。这个小软件有很多的功能，方便实用。本文介绍Mac OS 下使用Automator批量将图片转成pdf文件"
category: "Technique"
tags:
- Apple
- Mac
---

{% include JB/setup %} 

Automator是Mac OS X内建的一个应用程序，用于自动化处理很多重复的工作。这个小软件有很多的功能。方便实用。

1. 打开Automator，位于Application文件夹下，图标如下，可以看到他是一个小bot，自动帮你处理很多琐碎的事情。

![au](/assets/images/2009/11/automator.png)

2. 选择新建一个Workflow，完成一个工作流。可以看到Automator几乎涉及了系统常用操作中的很多流程。诸如iCal日历的事件处理，联系人，Mail等。

	![aum](/assets/images/2009/11/automator_main.png)

3. 我们要建立一个自动将图片转成pdf的流程


有人可能要问，你这个需求很变态阿。谁有这个要求呢?[哈哈，国外书太贵来。我的书都是从书店拍下来的，所以呢，为了方便阅读还是转成pdf版本的。]

使用Automator最大的难处是如果定义自动处理的流程。因为你是要一个小机器人帮你做事，所以必须按照步骤指定清楚。

本例中流程很简单:
- 允许Automator，提示用户输入图片(可以是一个包含有所要图片的一个文件夹，或者是支持multiple choose)
- 选择适合的Automator可以提供的批处理程序。    
- 设置批处理的要求，输出位置，格式，文件名等。



4. 运行

![aur](/assets/images/2009/11/automator_run.png)

流程部署完成后点击右上角的Run按钮。

![aure](/assets/images/2009/11/automator_result.png)

出现绿色图标说明运行无误。

![aup](/assets/images/2009/11/automator_pdf.png)

OK， 一份52页的pdf文件就生成来。

注意:

> 转化图像之前，图象的位置要事先调好。暂时还没有发现如果能够自动的调整图像。

Automator有非常多的功能，甚至可以记录(Record)用户的鼠标点击，然后自动执行。很强大的。记得某些游戏上需要自动点击的。不知道能不能用上。

还有可以通过观察Automator自带一系列流程来挖掘你自己需要的workflow。让你的生活变得更加轻松!

That's it!!
