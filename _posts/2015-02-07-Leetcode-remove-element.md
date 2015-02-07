---
layout: post
title: "Leetcode Remove element"
description: "Leetcode刷题有感 Leetcode Remove element"
category: "Technique"
tags:
- Algorithm
- Leetcode
---




> Given an array and a value, remove all instances of that value in place and return the new length.

> The order of elements can be changed. It doesn't matter what you leave beyond the new length.



同样的快慢指针思路：

版本一：

```Java
public int removeElement(int[] A, int elem) {
		if (A == null || A.length == 0) {
			return 0;
		}

		int walker = 0;
		int runner = 0;
		while (runner < A.length) { 
			if (A[runner] != elem) {
				A[walker++] = A[runner];
			}
			runner++;
		}

		return walker;
	}

```

需要注意的是，与[remove duplicates in sorted array](http://anotherbug.com/blog/2015/02/07/Leetcode-remove-duplicates-in-sorted-array/) 相比不一样的地方是 A[walker++]而非A[++walker]，为什么？【你需要好好思考下，walker和runner初始位置，以及第一次比较后它们值的变化。】
这个版本可以通过leetcode测试，也很完美，可以再优化了吗？


版本二：

```Java
  public int removeElement(int[] A, int elem) {
        if (A == null || A.length == 0) {
			return 0;
		}

		int walker = 0;
		int runner = 0;
		while (runner < A.length) {
			if (A[runner] == elem) {
			    runner++;
				continue;
			}
			A[walker++] = A[runner++];
		}

		return walker;
    }

```

版本二的if判读用的是==。因为毕竟要remove的element要少，if (A[runner] != elem) 次数要多，所以if (A[i] == elem) 从效率上更好。问二个问题。里面的if判断是否可以写成 if (A[runner++] == elem)?【不可以，后面重复A[runner++]导致加了2次】。另外，A[walker++] = A[runner++]可以这么写不会导致数组越界。








