---
layout: post
title: Ruby String 二则
tags:
- Ruby
- Technique
status: publish
type: post
published: true
meta:
  views: '816'
---
<p>Ruby确实好用，方便灵活。String操作功能很好很强大。实例二则。</p>  <p>&#160;</p>  <p><strong><font size="3">例1：判断一句话是否是回文。（汗，不是回族文字）</font></strong></p>  <p><em># check if a sentense is palindrome,case insensitives      <br />def palindrome?(string)</em></p>  <p><em>str = string.downcase.gsub(/\W/, &quot;&quot;)      <br />str1 = str.reverse       <br />str == str1</em></p>  <p><em>end</em></p>  <p><em># palindrome?(&quot;A man, a plan, a canal -- Panama&quot;)      <br /># palindrome?(&quot;Madam, I'm Adam!&quot;)       <br /># palindrome?(&quot;Abracadabra&quot;)</em></p>  <p>&#160;</p>  <p><font size="3"><strong>例2：统计一句话中单词出现词频</strong></font></p>  <p><em># count the number of word occurance, case insensitives      <br />def count_words(string)       <br />&#160; res={}       <br />&#160; string.downcase.gsub(/[^a-z\s]/,'').gsub(/\s\s/,' ').split(/\b\s/).map{|a| res[a] = res[a]? res[a]+1:1}       <br />&#160; res       <br />end</em></p>  <p><em>count_words(&quot;A man, a plan, a canal -- Panama&quot;)      <br />count_words(&quot;Doo bee doo bee doo&quot;)</em></p>
