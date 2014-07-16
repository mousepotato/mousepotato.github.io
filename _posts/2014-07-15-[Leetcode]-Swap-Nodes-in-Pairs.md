--- 
layout: post
title: (Leetcode) Swap Nodes in Pairs
description: "Swap Nodes in Pairs"
category: Technique
tags: 
- Programming 
- Leetcode
---



> Given a linked list, swap every two adjacent nodes and return its head.  
> For example, Given `1->2->3->4`, you should return the list as `2->1->4->3`.


This is a pointer problem, if you have a clear picture in mind it will be very easy to implement. See below the code and illustration picture that I draw.


<img src="/assets/images/2014/07/15/pointer.png" alt="pointer" style="width: 400px; height: 180px;"/>



```Java
public ListNode swapPairs(ListNode head) {
        ListNode p = new ListNode(0);
        p.next = head;
        head = p;
        while (true) {
            if (p.next == null)
                break;
            if (p.next.next == null)
                break;

            ListNode q1 = p.next;
            ListNode q2 = q1.next;
            q1.next = q2.next;
            q2.next = q1;
            p.next = q2;
            p = q1;

        }

        return head.next;
    }
```