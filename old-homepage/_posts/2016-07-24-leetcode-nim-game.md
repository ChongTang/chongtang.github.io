---
layout: post
title: "[LeetCode] Nim Game"
categories: leetcode
tags:
- leetcode
- math
---

**Question:**

You are playing the following Nim Game with your friend: There is a heap of stones on the table, each time one of you take turns to remove 1 to 3 stones. The one who removes the last stone will be the winner. You will take the first turn to remove the stones.

Both of you are very clever and have optimal strategies for the game. Write a function to determine whether you can win the game given the number of stones in the heap.

For example, if there are 4 stones in the heap, then you will never win the game: no matter 1, 2, or 3 stones you remove, the last stone will always be removed by your friend.

**Hints:**

1. If there are 5 stones in the heap, could you figure out a way to remove the stones such that you will always be the winner?

**Thoughts:**

According to the hint, there is no way to win if there are 4 stones. However, you can win if there are 5, 6, or 7 stones. You cannot if there are 8 stone, since this case is just like 4 stones case. As you can see, if the initial number of stones are multiplier of 4, there will be no way for you to win. That is to say, if ```n % 4 == 0```, you will lose for sure.

**Solution:**

{% highlight python %}
class Solution(object):
    def canWinNim(self, n):
        """
        :type n: int
        :rtype: bool
        """
        return n%4 > 0
{% endhighlight %}
 