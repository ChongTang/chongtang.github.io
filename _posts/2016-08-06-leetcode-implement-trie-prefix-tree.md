---
layout: post
title: "[LeetCode] Implement Trie (Prefix Tree)"
categories: leetcode
tags:
- leetcode
- tree
---
**Question**

Implement a trie with _insert_, _search_, and _startsWith_ methods.

**Solution**

{% highlight python %}
class TrieNode(object):
    def __init__(self):
        """
        Initialize your data structure here.
        """
        self.children = dict()
        self.isWord = False
        

class Trie(object):

    def __init__(self):
        self.root = TrieNode()

    def insert(self, word):
        """
        Inserts a word into the trie.
        :type word: str
        :rtype: void
        """
        node = self.root
        for letter in word:
            child = node.children.get(letter)
            if child is None:
                child = TrieNode()
                node.children[letter] = child
            node = child
        node.isWord = True
        
        

    def search(self, word):
        """
        Returns if the word is in the trie.
        :type word: str
        :rtype: bool
        """
        node = self.root
        for c in word:
            child = node.children.get(c)
            if child is None:
                return False
            node = child
        return node.isWord
                
        

    def startsWith(self, prefix):
        """
        Returns if there is any word in the trie
        that starts with the given prefix.
        :type prefix: str
        :rtype: bool
        """
        node = self.root
        for c in prefix:
            child = node.children.get(c)
            if child is None:
                return False
            node = child
        return True


# Your Trie object will be instantiated and called as such:
# trie = Trie()
# trie.insert("somestring")
# trie.search("key")
{% endhighlight %}
