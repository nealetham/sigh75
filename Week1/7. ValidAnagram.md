# ValidAnagram

## Initial Solution

I iteratively check through if every character in t is in s, and subsequently remove it from s. If a character is not found in s, it is not an anagram. The last check is to check if all elements have been removed from s.

This solution can definitely be improved.

Time Complexity: O(n)
Space Complexity: O(n)

```python
def isAnagram(self, s, t):
    string = list(s)
    for char in list(t):
        if char in string:
            string.remove(char)
        else:
            return False

    return len(string) == 0
```

<!-- ## Improved Solution -->

<!-- Description -->

<!-- Time Complexity: O() -->
<!-- Space Complexity: O() -->


<!-- ```python -->
<!-- ``` -->

<!-- Completed: dd/mm/yyyy -->