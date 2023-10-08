# Binary Search

## Initial Solution

Classic search problem solved iteratively.

Time Complexity: O(log(n))
Space Complexity: O(1)

```python
def search(self, nums, target):
  f_pointer = 0
  b_pointer = len(nums)-1
  
  while f_pointer <= b_pointer:
      mid_pointer = (f_pointer + b_pointer)//2
      value = nums[mid_pointer]
      if value == target:
          return mid_pointer
      elif value < target:
          f_pointer = mid_pointer + 1
      else:
          b_pointer = mid_pointer - 1

  return -1
```

Completed: 8/10/2023
