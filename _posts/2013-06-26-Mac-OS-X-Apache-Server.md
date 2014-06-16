---
layout: post
title: "Mac OS X 下开启apache web服务器"
description: "Mac OS X 下开启apache web服务器的方法"
category: "Technique"
tags: 
- Mac
---
{% include JB/setup %}  


Mac OS X 下开启apache web服务器

- 编辑配置文件.conf

		vim /etc/apache2/users/shuangjiang.conf
		

- 添加配置文件 `shuangjiang.conf`

		 <Directory "/Users/shuangjiang/Sites/">
		     Options Indexes MultiViews FollowSymlinks
		     AllowOverride All
		     Order allow,deny
		     Allow from all
		 </Directory>

- 重启和关闭 apache 服务器

> sudo apachectl start/stop  
> sudo apachectl restart

- 访问页面

		http://localhost/~shuangjiang