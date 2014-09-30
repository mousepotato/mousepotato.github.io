---
layout: post
title: "How to install mediatomb"
description: "Recently, I did some research on how to use my Mac as a DLNA Sever. Mediatomb is a popular software that you need to know. However, i got some problem to install it on my Mac OS X Snow Leopard."
category: "Technique"
tags:
- Mac
---


Recently, I did some research on how to use my Mac as a DLNA Sever. Mediatomb is a popular software that you need to know. However, i got some problem to install it on my Mac OS X Snow Leopard.

Typically, you use fink to install it as recommended.

> `fink selfupdate` 
 
> `fink scanpackages`
 
> `fink index`

> `fink install mediatomb`


However, I ended up with an error message saying "Information about 10180 packages read in 2 seconds. No package to install" WTF!! Several times.



Then, I thought Macports might work.

> `sudo port install mediatomb`
> 	

Wow, it works. I finally got MediaTomb UPnP Sever 0.11.0 install on my Mac. em ^_^.

That's it!!
