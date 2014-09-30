--- 
layout: post
title: (Leetcode) Palindrome Partitioning II
description: "Palindrome Partitioning II"
category: Technique
tags: 
- Programming 
- Leetcode
---



> Given a string s, partition s such that every substring of the partition is a palindrome.

Return the minimum cuts needed for a palindrome partitioning of s.

For example, given s = "aab",
Return 1 since the palindrome partitioning ["aa","b"] could be produced using 1 cut.


```
public int minCut(String s) {
        
        boolean[][] isPalindrome = getIsPalindrome(s);
        
        int n = s.length();
        // dp[i]表示前i个字符最少需要几次cut就能都变成回文
        int[] dp = new int[n + 1];
        //Arrays.fill(dp, Integer.MAX_VALUE);
        dp[0] = 0;
        
        for (int i = 1; i <= n; i ++){
            dp[i] = i;
            for (int j = 0; j < i; j++) {
                if(isPalindrome[j][i - 1]) {
                    dp[i] = Math.min(dp[i], dp[j] + 1);
                }
            }
        }
        
        return dp[n] - 1;
        
    }
	
	private boolean[][] getIsPalindrome(String s) {
		boolean[][] matrix = new boolean[s.length()][s.length()];

		for (int i = 0; i < s.length(); i++) {
			matrix[i][i] = true; // Diagonal is palindrome
		}

		for (int i = 0; i < s.length() - 1; i++) {
			matrix[i][i + 1] = (s.charAt(i) == s.charAt(i + 1));
		}

		for (int step = 2; step < s.length(); step++) {
			for (int start = 0; step + start < s.length(); start++) {
				matrix[start][start + step] = matrix[start + 1][start + step - 1] && (s.charAt(start) == s.charAt(start + step));
			}
		}

		return matrix;
	}
```