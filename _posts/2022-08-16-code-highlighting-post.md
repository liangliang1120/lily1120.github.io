---
layout: post
title: Algorithm-DFS
date: 2022-08-16
excerpt: "DFS"
tags: [Algorithm, code, Python]
comments: False
---

## DFS summary

{% highlight python %}
def dfs(curr):
  visited.add(curr)
  for next in curr.neighbors:
    if next not in visited:
      dfs(next)
{% endhighlight %}


## Scenes 
- Permutations
- Find out all the cases
---

## Tree DFS
### [104 Maxmum depth of binary tree](https://github.com/liangliang1120/leetcode/blob/main/solutions/0104-Maximum-Depth-of-Binary-Tree.py)
- if not root: 0; left_d=dfs(root.left); right_d=dfs(root.right);return max(left_d, right_d) + 1
- Time: O(N)
- DFS Space:O(height), BFS Space: worest case O(n)

### [543. Diameter of Binary Tree](https://github.com/liangliang1120/leetcode/blob/main/solutions/0543-Diameter-of-Binary-Tree.py)
- Glouble variable: self.d 
- dfs(root) for the **subtree longest depth**: if not root: 0; left_d=dfs(root.left); right_d=dfs(root.right); self.d = max(self.d, left_d +right_d); return max(left_d, right_d) + 1
- return self.d
- Time: O(n), 
- Space: O(height) (stack, recurse）
~~~ python
class Solution:
    def diameterOfBinaryTree(self, root: Optional[TreeNode]) -> int:
        self.res = 0
        def dfs(node):
            if not node:
                return 0
            left_d = dfs(node.left)
            right_d = dfs(node.right)
            self.res = max(self.res, left_d + right_d)
            return max(left_d, right_d) +1

        dfs(root)
        return self.res
~~~

## [124. Binary Tree Maximum Path Sum](https://github.com/liangliang1120/leetcode/blob/main/solutions/DFS_124.py)
- self.res = float("-inf")
- def max_sum_oneside(node):return max(0, max(left_s, right_s) + node.val)
- self.res = max(self.res, left_s + right_s + node.val)

~~~ python
class Solution:
    def maxPathSum(self, root: Optional[TreeNode]) -> int:
        self.res = float("-inf")
        def max_sum_oneside(node):
            if not node:
                return 0
            
            left_s = max_sum_oneside(node.left)
            right_s = max_sum_oneside(node.right)
            self.res = max(self.res, left_s + right_s + node.val)
            return max(0, max(left_s, right_s) + node.val)

        max_sum_oneside(root)
        return self.res
~~~

### [94 binary tree inorder traversal]# Definition for a binary tree node.
- time: O(n), space: O(height)

~~~ python
class Solution:
    def inorderTraversal(self, root: Optional[TreeNode]) -> List[int]:
        res = []
        def dfs(node):
            if not node:
                return
            
            dfs(node.left)
            res.append(node.val)
            dfs(node.right)

        dfs(root)
        return res
~~~

