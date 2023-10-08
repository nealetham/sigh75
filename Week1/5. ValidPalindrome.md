# Valid Palindrome

## Initial Solution

Here I used two pointers, one pointing towards the start of the array, and the other pointing towards the last index of the array. With eaach iteration, we encroach the pointers closer to each other, but on the condition that both elements are equal and alphanumeric. Supposing that either is non-alphanumeric, then we can just increment/decrement that pointer solely.

If at any point, the elements are not equal, then it is not a valid palindrome. Elsewise, once we have iterate through all elements, we guarantee that it is one.

I figure that this method would be more clean as compared to preprocessing of the string, which would require another pass.

Time Complexity: O(n)
Space Complexity: O(1)

```python
def isPalindrome(self, s):
    string = list(s.lower())
    fp, lp = 0, len(string) - 1
    while fp < lp:
        fc, lc = string[fp], lc = string[lp]
        if fc.isalnum() and lc.isalnum():
            if string[fp] == string[lp]:
                fp += 1
                lp -= 1
                continue
            return False
        
        if fc.isalnum():
            lp -= 1
        else:
            fp +=1
            
    return True
```

Completed: 6/10/2023