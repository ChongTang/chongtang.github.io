---
layout: post
title: "[LeetCode] Maximum Depth of Binary Tree"
categories: leetcode
tags:
- leetcode
- tree
---

**Question:**

Given a binary tree, find its maximum depth.

The maximum depth is the number of nodes along the longest path from the root node down to the farthest leaf node.

**Solution:**

{% highlight python %}
class Solution(object):
    def maxDepth(self, root):
        """
        :type root: TreeNode
        :rtype: int
        """
        if root == None:
            return 0
        else:
            return max(self.maxDepth(root.left), self.maxDepth(root.right))+1
{% endhighlight %}
