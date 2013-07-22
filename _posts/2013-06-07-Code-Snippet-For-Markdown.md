---
layout: post
title:  "How to blog using markdown efficiently"
description: "本文介绍如何高效的使用markdown文件来编写blog。"
category: "Technique"
tags:
- Markdown
---
{% include JB/setup %}

如何高效得使用markdown编辑blog


Markdown文件因为其plain text特性，被很多人青睐。诸如我们之前说的，可以用它来做报告，写PPT。参见[如何使用markdown做报告](http://anotherbug.com/blog/2013/06/12/how-to-make-presentation-using-markdown/)。 今天我们介绍如何高效得使用markdown编辑博客。

### 1. Insert colored text 
> `<p style="color: #ff0000;">这是一段红色的文字</p>`

结果：
> <p style="color: #ff0000;">这是一段红色的文字</p>

Other colors:  

	- <p style="color: #0000ff;">Blue #0000ff  </p> 
	- <p style="color: #008000;">Green #008000 </p>
	- <p style="color: #ff00ff;">Magenta #ff00ff </p>
结果：

- <p style="color: #0000ff;">Blue #0000ff  </p> 
- <p style="color: #008000;">Green #008000 </p>
- <p style="color: #ff00ff;">Magenta #ff00ff </p>

![Color Code](/assets/images/2013/06/07/color_code.png)

### 2. Insert table
	<table>
	  <tr>
	    <th>律法</th><th>基督</th>
	  </tr>
	  <tr>
	    <td>影儿</td><td>像（来10：1 ）</td>
	  </tr>
	  <tr>
	    <td>影儿</td><td>本体（西2：17）</td>
	  </tr>
	</table>

结果：
<table>
  <tr>
    <th>律法</th><th>基督</th>
  </tr>
  <tr>
    <td>影儿</td><td>像（来10：1 ）</td>
  </tr>
  <tr>
    <td>影儿</td><td>本体（西2：17）</td>
  </tr>
</table>

### 3. Using `<pre>`
	<pre>
	             ,-.
	    ,     ,-.   ,-.
	   / \   (   )-(   )
	   \ |  ,.>-(   )-<
	    \|,' (   )-(   )
	     Y ___`-'   `-'
	     |/__/   `-'
	     |
	     |
	     |    -hrr-
	  ___|_____________
	  
	</pre>

结果：

<pre>
             ,-.
    ,     ,-.   ,-.
   / \   (   )-(   )
   \ |  ,.>-(   )-<
    \|,' (   )-(   )
     Y ___`-'   `-'
     |/__/   `-'
     |
     |
     |    -hrr-
  ___|_____________
  
</pre>

