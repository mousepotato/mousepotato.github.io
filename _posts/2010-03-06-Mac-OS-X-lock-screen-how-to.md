---
layout: post
title: Mac OS下自动锁屏快捷键设置
tags:
- Apple
- Mac
- Technique
status: publish
type: post
published: true
meta:
  views: '646'
  _edit_last: '1'
---
<p><font face="'Courier New'" size="3"><span style="font-size: 13px;">用惯Windows的人都知道 "Win+L" 可以快速的锁定屏幕,一直纳闷Mac OS下没有,今天上网不幸搜到了一个.共享之:</span></font></p>
<p><font face="'Courier New'" size="3"><span style="font-size: 13px;">1.打开Automator--&gt;新建一个Service--&gt;选择右侧的"Run Shell Script"拖到左侧编辑区.在文本框中输入:</span></font></p>
<p><code><font face="'Courier New'" size="3"><span style="font-size: 13px;"><b><font color="#FF421F">'/System/Library/CoreServices/Menu Extras/User.menu/Contents/Resources/CGSession' -suspend</font></b></span></font></code></p>
<p><font color="#FF421F" face="'Courier New'" size="3"><span style="font-size: 13px;"><b><span style="font-weight: normal;"><font color="#000000">输入选择 no input,将service保存为"Lock Screen"</font></span><br /></b></span></font></p>
<p><font face="'Courier New'" size="3"><br /></font></p>
<div style="text-align: center;">
  <font face="'Courier New'" size="3"><span style="font-size: 13px;"><span style="font-size: medium;"><img src="/assets/uploads/2010/03/lock_screen.jpg" width="634" height="328" alt="lock_screen.png" /></span><br /></span></font>
</div>
<div style="text-align: center;">
  <font face="'Courier New'" size="3"><br /></font>
</div>
<div style="text-align: left;">
  <font><font face="'Courier New'" size="3"><span style="font-size: 13px;">2.打开System Preferences--&gt;keyboard--&gt;keyboard shortcuts 点击左侧的Service,拖到最下.选择LockScreen,双击输入快捷键,我的快捷键是:"Command-Control-L"</span></font></font>
</div>
<div style="text-align: left;">
  <font face="'Courier New'" size="3"><br /></font>

  <div style="text-align: center;">
    <font face="'Courier New'" size="3"><span style="font-size: medium;"><img src="/assets/uploads/2010/03/lock_shortcut.jpg" width="480" height="362" alt="lock_shortcut.png" /><br /></span></font>
  </div>

  <div style="text-align: left;">
    <font face="'Courier New'" size="3"><br /></font>
  </div>

  <div style="text-align: left;">
    <font><font><font face="'Courier New'" size="3"><span style="font-size: 13px;">以后输入"Command+Control+L"就可以锁屏了!</span></font></font></font>
  </div>

  <div style="text-align: left;">
    <font face="'Courier New'" size="3"><br /></font>
  </div>
</div>
