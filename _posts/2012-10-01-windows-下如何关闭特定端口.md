---
layout: post
title: Windows 下如何关闭特定端口
tags:
- Technique
status: publish
type: post
published: true
meta:
  views: '490'
---
<p><strong>1. netstat -aon|findstr &quot;9050&quot;</strong></p>  <p>&#160;</p>  <p>TCP: 127.0.0.1:9050 0.0.0.0 LISTENING 2016</p>  <p>&#160;</p>  <p><strong>2. tasklist|findstr &quot;2016&quot;</strong></p>  <p><strong></strong></p>  <p>tor.exe 2016 Console 0 16,064K</p>  <p>&#160;</p>  <p><strong>3. 然后ctrl+alt+delete 打开任务管理器，找到tor.exe右键end process. OK了。</strong></p>
