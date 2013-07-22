---
layout: post
title: "Ruby String 二则"
description: "Ruby String 例子"
category: "Technique"
tags:
- Ruby
- Programming
---
{% include JB/setup %} 

Ruby确实好用，方便灵活。String操作功能很好很强大。实例二则。


### 例1：判断一句话是否是回文。（汗，不是回族文字）

	# check if a sentense is palindrome,case insensitives 
	def palindrome?(string)
	str = string.downcase.gsub(/\W/, "") 
	str1 = str.reverse 
	str == str1
	end
	# palindrome?("A man, a plan, a canal -- Panama") 
	# palindrome?("Madam, I'm Adam!") 
	# palindrome?("Abracadabra")




### 例2：统计一句话中单词出现词频

	# count the number of word occurance, case insensitives 
	def countwords(string) 
	  res={} 
	  string.downcase.gsub(/[^a-z\s]/,'').gsub(/\s\s/,' ').split(/\b\s/).map{|a| res[a] = res[a]? res[a]+1:1} 
	  res 
	end
	countwords("A man, a plan, a canal -- Panama") 
	count_words("Doo bee doo bee doo")