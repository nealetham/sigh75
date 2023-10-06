# Valid Parantheses

## Initial Solution

My initial solution was to maintain a stack. For every open parantheses we push the element to the stack, and for each closing parantheses, we pop from the stack and compare if the two are the same type of brackets. If they are, we continue on to the next element, else we know that there is a violation.

There are two edge cases.
1. No opening parantheses. We can immediately return false.
2. No closing parantheses. We need to check if the stack is empty after all elements have been processed.

Time Complexity: O(n)
Space Complexity: O(n)

The space complexity is O(n) to account for the fact when all the input parantheses are either open or close.

```python
def isValid(self, s):
    input_para = list(s)
    open_para = ['(', '{', '[']
    stack = []
    for parantheses in input_para:
        if parantheses in open_para:
            stack.append(parantheses)
            continue
        
        if len(stack) == 0:
            return False
        
        top_of_stack = stack.pop()
        if top_of_stack == '(' and parantheses == ')':
            continue
        if top_of_stack == '{' and parantheses == '}':
            continue
        if top_of_stack == '[' and parantheses == ']':
            continue
        return False

    return len(stack) == 0
```

<!-- ## Improved Solution -->

<!-- Description -->

<!-- Time Complexity: O() -->
<!-- Space Complexity: O() -->


<!-- ```python -->
<!-- ``` -->

Completed: 6/10/2023