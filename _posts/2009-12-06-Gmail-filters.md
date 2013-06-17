---
layout: post
title: Gmail的filter功能
tags:
- Gmail
- Google
status: publish
type: post
published: true
meta:
  _edit_last: '1'
  views: '987'
---
Gmail的filter功能结合label使用可以使原本很强大的mail变的更加有秩序和易于管理。最初的filter功能只能对未来的邮件进行管理，无法对自动对已有的邮件进行管理。现在可以对现有的邮件和可能会收到的邮件均可以自动化管理。

<h3>一、Gmail Filter可以做什么</h3>

<strong>1.用于自动对邮件设置label，进行分类:</strong>



比如将所有从ebay发来的消息或者 paypal发来的消息,标记为Shopping标记

<p style="text-align: center;"><img src="/assets/uploads/2009/12/shopping_filter.jpg" alt="shopping_filter.png" width="480" height="31" /></p>

<strong>2.用于对特殊邮件的转发:</strong>

<ul>

	<li>对某些重要的邮件可以专门转发到某个特定邮箱以便保存,还有一种情况是针对所有邮件都进行转发.比如当初用139邮箱的免费短信提醒的时候可以将Gmail收到的邮箱全部转发到139 mail中.</li>

	<li>某些信息可能是多个人共享的,这时候可以设置转发给对方.</li>

</ul>

<p style="text-align: center;"><img src="/assets/uploads/2009/12/filter_forward.jpg" alt="filter_forward.png" width="480" height="47" /></p>

<p style="text-align: left;">这个filter是将所有从KUB发过来的电费信息以及Sprint的手机费信息以及宿舍公告统统转发给我的室友~,用于共享信息.</p>

<strong>3.用于对特殊邮件的归档(Archive):</strong>



Gmail的归档(Archive)是指不将邮件显示在收信箱中.

<div style="text-align: center;">

<img src="/assets/uploads/2009/12/gmail_archive.jpg" alt="gmail_archive.png" width="480" height="25" /></div>

<div style="text-align: left;">可以在All Mail中显示. 由于gmail可以支持一个邮箱多个帐号.比如你的邮箱名是abc@gmail.com,那么abc+aaaa@gmail.com也会是你的邮箱.这就给分类提供了可能,加上gmail的超大空间. 可以用来存储一些个人文件或者文档. 当然这些存储的东西是为了备份或者方便以后查找,所以可以直接归档.</div>

<div style="text-align: left;">

<div style="text-align: center;">

<img src="/assets/uploads/2009/12/archive_filter.jpg" alt="archive_filter.png" width="467" height="43" /></div>

<div style="text-align: left;">如上,建立一个filter,功能是对发送到自己的gmail中的文档自动归档并加上File标签,同时不会设置为垃圾邮件.</div>

</div>

<strong>4.用于对特殊邮件的删除:</strong>



可以针对某个网站的或者某个特定邮箱的邮件进行过滤.可以直接删除邮件,避免某些麻烦或者被垃圾邮件困扰.如下,删除一个特定网站的垃圾邮件.

<p style="text-align: center;"><img src="/assets/uploads/2009/12/filter_delete.jpg" alt="filter_delete.png" width="247" height="43" /></p>

<p style="text-align: left;"></p>

<p style="text-align: left;"></p>



<h3>二、Filter如何创建和书写</h3>

<strong>1.三种方式可以新建一个Filter:</strong><strong>

</strong>

a).首页搜索框右下角,

<div style="text-align: center;"><img src="/assets/uploads/2009/12/create_filter.jpg" alt="create_filter.png" width="305" height="53" /></div>

b).Setting里面点击Filter项,

<p style="text-align: center;"><img src="/assets/uploads/2009/12/filter_create_1.jpg" alt="filter_create_1.png" width="480" height="70" /></p>

c).收到邮件后点击action项下的Filter messages like these.



<!--more-->

<div style="text-align: center;">

<img src="/assets/uploads/2009/12/filter_create_2.jpg" alt="filter_create_2.png" width="172" height="171" /></div>

<div style="text-align: left;"></div>

<div style="text-align: left;"><strong>2.Filter 书写的格式:</strong></div>

<div style="text-align: left;"><strong>

</strong></div>

<div style="text-align: left;">常用到的就是设置邮件的来源(From),目的(To),已经可以通过关键词和附件进行过滤.</div>

<p style="text-align: center;"><img src="/assets/uploads/2009/12/filter_1.jpg" alt="filter_1.png" width="699" height="110" /></p>

Filter支持的几个符号.具体可以参考 <a title="Gmail Help" href="http://mail.google.com/support/bin/answer.py?answer=7190">Gmail Help</a>.



a). '*'星号,通配符



比如所有从amazon.com发来的邮件,可以写成 *@amazon.com,从eaby发来的邮件,*@ebay.com,或者*.voice.google.com,表示所有发信人以voice.google.com结尾的邮件.



b).' |' 或者 OR



可以连接多个条件,比如建立一个shopping的标签,<a href="mailto:*@amazon.com%7C*@ebay.com%7C*@paypal.com%7C*@barnesandnoble.com"><span style="font-size: medium;">*@amazon.com|*@ebay.com|*@paypal.com|*@barnesandnoble.com</span></a><span style="font-size: medium;">" <span style="font-size: 12px;">使用 '|' 可以减少filter建立的数量,同时也更加美观.</span></span>



c). '-' 排除号,减号



当你需要从某一个建立好的filter中排除某些查询条件是,可以使用'-'.

<div style="text-align: center;"><img src="/assets/uploads/2009/12/filter_complicated.jpg" alt="filter_complicated.png" width="610" height="31" /></div>

<div style="text-align: left;">一个比较全的filter.使用了以上三种符号.</div>
