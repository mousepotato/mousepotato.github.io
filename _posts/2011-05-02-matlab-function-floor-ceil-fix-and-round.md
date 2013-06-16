---
layout: post
title: Matlab 里面floor, ceil, fix 和 round函数
tags:
- Matlab
- Research

---

## **floor：朝负无穷方向舍入**
> `B = floor(A)` rounds the elements of A to the nearest integers less than or equal to A.

## **ceil：朝正无穷方向舍入**
> `B = ceil(A)` rounds the elements of A to the nearest integers greater than or equal to A.

## **fix：朝零方向舍入**
> `B = fix(A)` rounds the elements of A toward zero, resulting in an array of integers.

## **round：四舍五入**
> `B = round(A)` rounds the elements of X to the nearest integers.

## **Example：**

> a= [-0.9,    -2.1,    -0.4,    0.3,    0.8,    1.1,    2.7,    -1.2+2.9i];
 
> floor(a)=[ -1,      -3,      -1,      0,      0,      1,      2,       -2+2i]
 
> ceil(a)= [ 0,       -2,       0,      1,      1,      2,      3,       -1+3i]

> fix(a)= [ 0,       -2,       0,      0,      0,      1,      2,       -1+2i]

> round(a)=[-1,       -2,       0,      0,      1,      1,      3,       -1+3i]

注：For complex X, for all the four fuctions the imaginary and real parts are rounded independently.
