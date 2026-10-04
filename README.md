# All-Elements-in-Two-Binary-Search-Trees
# Definition for a binary tree node.
# class TreeNode:
#     def __init__(self, val=0, left=None, right=None):
#         self.val = val
#         self.left = left
#         self.right = right
class Solution:
    def getAllElements(self, root1: TreeNode | None, root2: TreeNode | None) -> list[int]:
        if root1 is None and root2 is None:
            return None
        r=[]
        def add(root,r):
            if root is None:
                return 
            add(root.left,r)
            r.append(root.val)
            add(root.right,r)
        add(root1,r)
        add(root2,r)
        r.sort()
        return r
