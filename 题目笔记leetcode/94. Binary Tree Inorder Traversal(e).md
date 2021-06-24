## 
94. Binary Tree Inorder Traversal

https://leetcode.com/problems/binary-tree-inorder-traversal/

My Solution

```python
# Definition for a binary tree node.
# class TreeNode:
#     def __init__(self, val=0, left=None, right=None):
#         self.val = val
#         self.left = left
#         self.right = right
class Solution:
    def inorderTraversal(self, root: TreeNode) -> List[int]:
        res = []
        def dsf(root):
            nonlocal res
            if not root:
                return 
            dsf(root.left)
            res.append(root.val)
            dsf(root.right)
        
        res = list()
        dsf(root)
        return res                
```

## 思路想法
学习了tree基本的架构以及遍历方式，递归和迭代是tree的重点。

## syntax notes
return 空: 结束函数的执行，从函数返回

return 与return None相同，返回值为None
