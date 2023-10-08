# Two Sum

## Initial Solution

The simplest and most naive solution is to use a nested for loop which iterates through the given list twice. 

Time Complexity: O(n^2)
Space Complexity: O(1)

```python
def twoSum(self, nums, target):
    for idx, x in enumerate(nums):
        for idy, y in enumerate(nums):
            if idx == idy:
                continue
            if x + y == target:
                return (idx, idy)
```

## Improved Solution

The naive solution involved n^2 computations, many of which are redundant. Instead, knowing that the previous element is not part of the solution, we only compare with elements that succeed it.

Time Complexity: O(n^2)
Space Complexity: O(1)

Though the time complexity is also bounded by n^2, it is more accurate to describe it as partial sums (i.e. 1 + 2 + ... + n).

```python
def twoSum(self, nums, target):
    for idx, x in enumerate(nums):
        desired_value = target-x
        if desired_value in nums[idx+1:]:
            pa = nums[idx+1:].index(desired_value)
            return (idx, pa+idx+1)
```

Completed: 6/10/2023