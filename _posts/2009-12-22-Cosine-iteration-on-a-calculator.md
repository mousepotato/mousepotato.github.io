---
layout: post
title: 对"输入计算器一个数字,然后狂按cosine"结果的思考
tags:
- Research
status: publish
type: post
published: true
meta:
  views: '628'
  _edit_last: '1'
---
高中的时候就这么做了.然后很奇怪的发现:当你狂按n次,(n&gt;20?未验证),你会发现计算器上显示的结果不变了~



一般你这么做了计算器会显示:<span style="font-family: Verdana, Arial, Helvetica, sans-serif; line-height: 22px;">0.999847741(很佩服用这个数做密码的人,这样忘记密码也不担心勒~),极少有人会得出:0.739085133215161(用这个密码似乎更保险).但是这两个结果都是对的.主要区别是你输入的数字表示的是十进制数字还是弧度.因为默认是十进制数字所以结果是第一种的人较多.在rad(弧度)的情况下,得出的结果是第二种,即:0.739085133215161.</span>



<strong>一.数学过程</strong>



<span style="font-family: Verdana; font-size: small;"><span style="font-size: 13px; line-height: 22px;">考虑输入弧度: x, 求余弦得出:cos(x).对结果再次求余弦得出:cos(cos(x)),如此反复,cos(...cos(cos(cos(x)))). 这是一个迭代过程. 迭代过程的一般解法是只需考虑初始值和前一个循环过程:</span></span>



<span style="font-family: Verdana, Arial, Helvetica, sans-serif;"><span style="line-height: 22px;">(a) x ---- cos(<span style="color: #ff6f42;">x</span>)</span></span>



<span style="font-family: Verdana, Arial, Helvetica, sans-serif;"><span style="line-height: 22px;">(b) cos(x)----cos(<span style="font-family: Verdana; font-size: small;"><span style="font-size: 13px;"><span style="color: #ff7445;">cos(x)</span></span></span>)</span></span>



<span style="font-family: Verdana, Arial, Helvetica, sans-serif;"><span style="line-height: 22px;">把(b)式中的<span style="font-size: 13px; color: #ff7445;">cos(x)</span>和(a)中的<span style="color: #ff6f42;">x<span style="color: #000000;">关联起来,即 <span style="font-size: 13px; color: #ff7445;">x<span style="color: #000000; font-size: 12px;">=<span style="font-size: 13px; color: #ff7445;">cos(x) <span style="color: #000000; font-size: 12px;">,那么这个迭代就可以简化成(a)了.所以,可以推出结论:输入计算器一个数字,然后狂按cosine,实际上是用暴力方法(brute force)解x=cos(x)这个方程.</span></span></span></span></span></span></span></span>



<strong>二.x=cos(x)这个方程有解么?</strong>



<span style="font-family: Verdana, Arial, Helvetica, sans-serif;"><span style="line-height: 22px;"><span style="font-family: Verdana; font-size: 13px; font-weight: bold;"><span style="font-weight: normal;">首先当然要定义范围.余弦函数周期是2pi.可以定义[0,2*pi],不过因为cos(x)值域不会超过1.范围可以进一步缩小.[0,pi/2]是一个不错的选择.</span></span></span></span>



<span style="font-family: Verdana, Arial, Helvetica, sans-serif; font-size: small;"><span style="font-size: 13px; line-height: 22px;">现在考虑函数f(x)=x-cos(x), xϵ[0,pi/2].方程x=cos(x)是否有解的问题,可以变换为f(x)的极值问题.</span></span>



<span style="font-family: Verdana, Arial, Helvetica, sans-serif; font-size: small;"><span style="font-size: 13px; line-height: 22px;">因为:f'(x)=1+sin(x)&gt;0, (f''(x)=cos(x)&gt;0,极小值在f(x0)=1+sin(x0)=0,处取得,不与关注.)一阶倒数大于零.所以f(x)单调递增.极大值在pi/2处取得.</span></span>



<span style="font-family: Verdana, Arial, Helvetica, sans-serif; font-size: small;"><span style="font-size: 13px; line-height: 22px;">max{f(x)}=f(pi/2)=pi/2 &gt; 0. 此时不能说f(x)=0有解,仍要考虑min{f(x)}与0的关系.只有min{f(x)}小于0,然后依据高数中的中值定理才可.min{f(x)}=f(0)=-1 &lt;0.</span></span>



<span style="font-family: Verdana, Arial, Helvetica, sans-serif; font-size: small;"><span style="font-size: 13px; line-height: 22px;">至此:因为f(x)=x-cos(x)在[0,pi/2]区间上连续且单调递增.min{f}&lt;0且max{f}&gt;0.所以必然存在x,使得 f(x)=0.</span></span>



<span style="font-family: Verdana, Arial, Helvetica, sans-serif; font-size: small;"><span style="font-size: 13px; line-height: 22px;"><strong>三.Matlab程序模拟</strong></span></span>

<div style="text-align: center;"><span style="font-family: Verdana, Arial, Helvetica, sans-serif; font-size: small;"><span style="font-size: 13px; line-height: 22px;"><strong>

<img src="/assets/uploads/2009/12/matlab_x_cosx.jpg" alt="matlab_x_cosx.png" width="448" height="209" /></strong></span></span></div>

<div style="text-align: left;"><span style="font-family: Verdana, Arial, Helvetica, sans-serif; font-size: small;"><span style="font-size: 13px; line-height: 22px;">设置了一个100次循环,if判断是用来给出第一个解.结果如下</span></span></div>

<div style="text-align: center;">



<span style="font-family: Verdana, Arial, Helvetica, sans-serif; font-size: small;"><span style="font-size: 13px; line-height: 22px;"><strong> </strong></span></span>



<strong> </strong><strong><img src="/assets/uploads/2009/12/matlab_x_cosx_result.jpg" alt="matlab_x_cosx_result.png" width="295" height="168" /></strong>



</div>

<div style="text-align: left;"><span style="font-family: Verdana, Arial, Helvetica, sans-serif; font-size: small;"><span style="font-size: 13px; line-height: 22px;">完整的matlab代码点此下载.<a title="testCosine" href="http://anotherbug.com/testCosine.m">testCosine.m</a></span></span></div>

<span style="font-family: Verdana, Arial, Helvetica, sans-serif; font-size: small;"><span style="font-size: 13px; line-height: 22px;"><strong><span style="font-family: Courier, Arial, Helvetica, sans-serif; font-size: small;"><span style="font-size: 12px; font-weight: normal; line-height: normal;"><span style="font-family: Verdana, Arial, Helvetica, sans-serif; font-size: 13px; font-weight: bold; line-height: 22px;">四.问题</span></span></span></strong></span></span>



<strong><span style="font-family: Courier, Arial, Helvetica, sans-serif; font-size: 12px; font-weight: normal; line-height: normal;">很多人可能要问那狂按计算器上的sin有没有稳定结果来?遇到这种情况借你计算器的人可要倒霉了.估计他以后没法算sin了,那个键失灵勒~.</span></strong>



<strong> </strong>



<strong><span style="font-family: Courier, Arial, Helvetica, sans-serif; font-size: small;"><span style="font-size: 12px; font-weight: normal; line-height: normal;">x=sin(x)在[0,pi/2]上是没有解的.可以用我第二部分的分析,同样分析这个.我的matlab代码里面注释了一段程序,同时话出了f(w)=w-sin(w)的图形.可以看出.在w&gt;0范围内.该图形都在w轴上方,即f(w)&gt;0.</span></span><span style="font-family: Courier, Arial, Helvetica, sans-serif; font-size: small;"><span style="font-size: 12px; font-weight: normal; line-height: normal;">当然,如果你觉得看完这篇blog非要找个例子试试,不然就连数羊,数什么都无法入眠的话我还是可以给你提供一个例子的.有兴趣的朋友可以尝试解下:<span style="font-family: Verdana, Arial, Helvetica, sans-serif; line-height: 22px;">e^x = 3x.(Hint:答案不唯一哦!)</span></span></span></strong>



<span style="font-family: Verdana, Arial, Helvetica, sans-serif; font-size: small;">

</span>
