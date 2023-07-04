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

### [543. Diameter of Binary Tree](https://github.com/liangliang1120/leetcode/blob/main/solutions/0543-Diameter-of-Binary-Tree.py)
- Glouble variable: self.d 
- dfs(root) for the subtree longest diameter: if not root: 0; left_d=dfs(root.left); right_d=dfs(root.right); self.d = max(self.d, left_d +right_d); return max(left_d, right_d) + 1
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





