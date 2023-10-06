# Problem Name

## Initial Solution

We use recursion to solve this problem by recursively swapping the two child nodes.

Time Complexity: O(n)
Space Complexity: O(n)

If the tree were to be balanced, the time and space complexity can be reduced to O(log(n))

```python
def invertTree(self, root):
    if root is None:
        return

    temp = root.right
    root.right = self.invertTree(root.left)
    root.left = self.invertTree(temp)
    return root
```

Completed: 6/10/2023