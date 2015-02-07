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
public int removeDuplicates(int [] A){
 		if (A == null || A.length == 0) {
			return 0;
		}
		int size = 0;
		int i = 0;
		while (i < A.length){
			if (A[size] != A[i]) {
				A[++size] = A[i];
			}
			i++;
		}
	
	    return size + 1;		
}

```
版本二通过测试，也使用了有意义的变量size作为输出。但是这个代码还是反应不出作者的思想和对题目的理解。

版本三：

```Java
	public int removeDuplicates(int[] A) {
		if (A == null || A.length == 0) {
			return 0;
		}

		int walker = 0;
		int runner = 0;
		while (runner < A.length) {
			if (A[runner] != A[walker]) {
				A[++walker] = A[runner];
			}
			runner++;
		}
		return walker + 1;
	}
```
版本三，变量使用了runner和walker，一看就明白是写代码者理解题目的快慢指针的思想。堪称完美。

此乃刷题者三种境界，共勉！








