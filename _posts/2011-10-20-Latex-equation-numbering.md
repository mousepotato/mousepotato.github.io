---
layout: post
title: Latex 公式编号
tags:
- Research
- Latex
status: publish
---

如果不想用自动标号,而是用自己的标号代替比如，  

![equation](/assets/uploads/2011/10/image9.png)  


代码如下：

	\begin{equation}
	    ... **\tag**{\textrm{Sparse Recovery}} \nonumber
	\end{equation}


使用 <font color="#ff0000">\tag 命令.