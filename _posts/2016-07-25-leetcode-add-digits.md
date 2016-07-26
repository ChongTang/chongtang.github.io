---
layout: post
title: "[LeetCode] Add Digits"
categories: leetcode
tags:
- leetcode
- math
---

**Question:**

Given a non-negative integer ```num```, repeatedly add all its digits until the result has only one digit.

For example:

Given ```num = 38```, the process is like: ```3 + 8 = 11```, ```1 + 1 = 2```. Since ```2``` has only one digit, return it.

**Follow up:**

Could you do it without any loop/recursion in O(1) runtime?

**Hint:**

1. A naive implementation of the above process is trivial. Could you come up with other methods?
2. What are all the possible results?
3. How do they occur, periodically or randomly?
4. You may find this [Wikipedia article](https://en.wikipedia.org/wiki/Digital_root) useful.

**Thoughts:**

A naive implementation would be getting every digit by mode 10, and add them together. But can we do better without a loop?
If you writing down some numbers from 10 to 28, you will find out that the answer 1 to 9 happen periodically.
+ ```10 -> 1```
+ ```11 -> 2```
+ .
+ .
+ .
+ ```17 -> 8```
+ ```18 -> 9```
+ ```19 -> 1```
+ ```20 -> 2```
+ .
+ .
+ .
+ ```26 -> 8```
+ ```27 -> 9```
+ ```28 -> 1```

So far, maybe you are thinking about ```num % 9```. Actually, you are right! But when you do ```num % 9```, you will not get the
right answers when the given number is like ```18``` or ```27```. If we want to get the right answer for all numbers, we can do
```(num-1) % 9 + 1```, and that's the final solution here.

**Solution:**

{% highlight java %}
public class Solution {
    public int addDigits(int num) {
        return (num-1)%9+1;
    }
}
{% endhighlight %}
