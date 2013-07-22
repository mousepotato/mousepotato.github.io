---
layout: post
title: "1001 Movies You Must See Before You Die"
description: "1001 Movies You Must See Before You Die"
category: "Technique"
tags:
- Life
- Ruby
- Movie
---
{% include JB/setup %} 

网上看到了这个Movie list，想保存下来一一观看。无奈没现成的excel格式。所以，自己动手丰衣足食。这次用的语言是Ruby。15行代码：

	require 'csv' 
	x=1 
	CSV.open('data.csv','w') do |data|
	
	    output = StringIO.new("", "w") 
	    # make excel using utf8 to open csv file 
	    head = 'EF BB BF'.split(' ').map{|a|a.hex.chr}.join() 
	    output.write(head)
	
	    data<<['id','Movie Name','Moive Name (in Chinese)'] 
	    File.open('101m.txt').eachline{ |s| 
	        data<<[x.tos(), s.split(")").first+")", s.split(")").last] 
	        x+=1; 
	    } 
	end
 


效果是这样子的：

  ![1000movie](/assets/uploads/2013/02/image.png)
  
