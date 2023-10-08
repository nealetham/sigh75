# Lowest Common Ancestor of a Binary Search Tree

## Initial Solution

A binary search tree has the property where the root is always larger than the left subtree, and smaller than the right subtree. Due to this property, we can solve this problem. There are only a few possiblities (i) p and q are greater than the root; (ii) p and q are lesser than the root; (iii) the root is between p and q; and (iv) either p or q are the root (by definition).

As such by handling these conditions, we either recurse on the left subtree, right subtree or return the root.

Time Complexity: O(n)
Space Complexity: O(n)

Assuming that the tree is unbalanced.

```python
def lowestCommonAncestor(self, root, p, q):
  left = min(p.val, q.val)
  right = max(p.val, q.val)
  
  if (root.val >= left and root.val <= right):
      return root

  if (p.val < root.val and q.val < root.val ):
      return self.lowestCommonAncestor(root.left, p, q)

  if (p.val > root.val and q.val > root.val):
      return self.lowestCommonAncestor(root.right, p, q)
```

Completed: 8/10/2023
