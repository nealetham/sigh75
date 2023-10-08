# Merge Two Sorted Lists

## Recursive Solution

My initial solution was to use recursion. We first settle the base cases, which occur when one list has ended. This becomes more apparent if you come from the perspective where one list is longer than the other, then you would intuitively return the list that is not empty.

Next we settle the head of the nodes, and with wishful thinking, we recurse on the tail of the list whose head was smaller, and the entire of the other list.

Time Complexity: O(n+m)
Space Complexity: O(n+m)

Where n = length of list1, and m = length of list2.

```python
def mergeTwoLists(self, list1, list2):
    if list1 is None:
        return list2
    
    if list2 is None:
        return list1

    if list1.val >= list2.val:
        list2.next = self.mergeTwoLists(list1, list2.next)
        return list2
    
    if list1.val <= list2.val:
        list1.next = self.mergeTwoLists(list1.next, list2)
        return list1
```

## Iterative Solution

The iterative solution uses a dummy node and a temp node to aid in traversing the linked lists, while maintaining a pointer to the head. The iterative solution is not vastly different from the recursive one.

Time Complexity: O(n+m)
Space Complexity: O(1)

Where n = length of list1, and m = length of list2.

```python
def mergeTwoLists(self, list1, list2):
    new_head = temp = ListNode(0)
    while list1 is not None and list2 is not None:
        if list1.val >= list2.val:
            temp.next = list2
            list2 = list2.next
        else:
            temp.next = list1
            list1 = list1.next

        temp = temp.next

    if list1 is not None:
        temp.next = list1
    else:
        temp.next = list2

    return new_head.next
```

Completed: 6/10/2023