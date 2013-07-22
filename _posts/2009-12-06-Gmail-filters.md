---
layout: post
title: "Gmail的filter功能"
description:"Gmail的filter功能结合label使用可以使原本很强大的mail变的更加有秩序和易于管理。最初的filter功能只能对未来的邮件进行管理，无法对自动对已有的邮件进行管理。现在可以对现有的邮件和可能会收到的邮件均可以自动化管理。"
category: "Technique"
tags:
- Google
---

{% include JB/setup %}  

Gmail的filter功能结合label使用可以使原本很强大的mail变的更加有秩序和易于管理。最初的filter功能只能对未来的邮件进行管理，无法对自动对已有的邮件进行管理。现在可以对现有的邮件和可能会收到的邮件均可以自动化管理。

## 一、Gmail Filter可以做什么

**1.用于自动对邮件设置label，进行分类:**



比如将所有从ebay发来的消息或者 paypal发来的消息,标记为Shopping标记

![shopping_filter](/assets/uploads/2009/12/shopping_filter.jpg)

**2.用于对特殊邮件的转发:**

- 对某些重要的邮件可以专门转发到某个特定邮箱以便保存,还有一种情况是针对所有邮件都进行转发.比如当初用139邮箱的免费短信提醒的时候可以将Gmail收到的邮箱全部转发到139 mail中.

- 某些信息可能是多个人共享的,这时候可以设置转发给对方.

![filter_forward](/assets/uploads/2009/12/filter_forward.jpg)

这个filter是将所有从KUB发过来的电费信息以及Sprint的手机费信息以及宿舍公告统统转发给我的室友~,用于共享信息。


**3.用于对特殊邮件的归档(Archive):**



Gmail的归档(Archive)是指不将邮件显示在收信箱中.


![gmail_archive](/assets/uploads/2009/12/gmail_archive.jpg)


可以在All Mail中显示. 由于gmail可以支持一个邮箱多个帐号.比如你的邮箱名是abc@gmail.com,那么abc+aaaa@gmail.com也会是你的邮箱.这就给分类提供了可能,加上gmail的超大空间. 可以用来存储一些个人文件或者文档. 当然这些存储的东西是为了备份或者方便以后查找,所以可以直接归档.


![archive_filter](/assets/uploads/2009/12/archive_filter.jpg)



如上,建立一个filter,功能是对发送到自己的gmail中的文档自动归档并加上File标签,同时不会设置为垃圾邮件.



**4.用于对特殊邮件的删除:**


可以针对某个网站的或者某个特定邮箱的邮件进行过滤.可以直接删除邮件,避免某些麻烦或者被垃圾邮件困扰.如下,删除一个特定网站的垃圾邮件.

![filter_delete](/assets/uploads/2009/12/filter_delete.jpg)


## 二、Filter如何创建和书写 ##

**1.三种方式可以新建一个Filter:**


- 首页搜索框右下角,

![create_filter](/assets/uploads/2009/12/create_filter.jpg)

- Setting里面点击Filter项,

![filter_create_1](/assets/uploads/2009/12/filter_create_1.jpg)


- 收到邮件后点击action项下的Filter messages like these.

![filter_create_2](/assets/uploads/2009/12/filter_create_2.jpg)


**2.Filter 书写的格式**


常用到的就是设置邮件的来源(From),目的(To),已经可以通过关键词和附件进行过滤

![filter_1](/assets/uploads/2009/12/filter_1.jpg)

Filter支持的几个符号.具体可以参考 
[Gmail Help](http://mail.google.com/support/bin/answer.py?answer=7190)



- '*'星号,通配符



比如所有从amazon.com发来的邮件,可以写成 *@amazon.com,从eaby发来的邮件,*@ebay.com,或者*.voice.google.com,表示所有发信人以voice.google.com结尾的邮件.



-' |' 或者 OR



可以连接多个条件,比如建立一个shopping的标签,<a href="mailto:*@amazon.com%7C*@ebay.com%7C*@paypal.com%7C*@barnesandnoble.com"><span style="font-size: medium;">*@amazon.com|*@ebay.com|*@paypal.com|*@barnesandnoble.com</span></a><span style="font-size: medium;">" <span style="font-size: 12px;">使用 '|' 可以减少filter建立的数量,同时也更加美观.</span></span>



- '-' 排除号,减号



当你需要从某一个建立好的filter中排除某些查询条件是,可以使用'-'.

![filter_complicated](/assets/uploads/2009/12/filter_complicated.jpg)

一个比较全的filter.使用了以上三种符号.
