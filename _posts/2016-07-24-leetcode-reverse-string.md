---
layout: post
title: "[LeetCode] Reverse String"
categories: leetcode
tags:
- leetcode
- string
---

**Question:**

Write a function that takes a string as input and returns the string reversed.

**Example**:

Given s = "hello", return "olleh".

**Solution:**

{% highlight python %}
class Solution(object):
    def reverseString(self, s):
        """
        :type s: str
        :rtype: str
        """
        return ''.join([s[x] for x in range(len(s)-1, -1, -1)])
{% endhighlight %}
 