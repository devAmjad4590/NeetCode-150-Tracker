
# [Merge Two Sorted Linked Lists]

- **Problem Number**: 21
- **Difficulty**: Easy
- **Pattern**: Linked List Iteration

---

### Key Insight

- O(n + m) where n is list1 and m is list2. O(1) Memory
- We create a new list with a dummy node, then iterate through both lists and compare the smaller values. The smaller node will be attached to the next pointer of the new list. Eventually, one of the lists (list1 and list2) will iterate to the end of the Linked List. So, we simply fill up the rest of the other existing lists to the new list. This will handle the edge case of this problem in which one or both of the linked lists might be empty.

---

### Solution

```python
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, val=0, next=None):
#         self.val = val
#         self.next = next
class Solution:
    def mergeTwoLists(self, list1: Optional[ListNode], list2: Optional[ListNode]) -> Optional[ListNode]:
        new_list = ListNode(0)
        head = new_list
        while list1 and list2:
            if list1.val < list2.val:
                new_list.next = list1
                list1 = list1.next
            else:
                new_list.next = list2
                list2 = list2.next
            new_list = new_list.next
        new_list.next = list1 or list2
        return head.next
```

---

### Spaced Repetition

- **Next Review Date**: 2026-01-27
- **Review Log**:
    - 2026-01-26 - Solved
    - YYYY-MM-DD - Reviewed

### Review Reptitions
- [ ] 1st Review
- [ ] 2nd Review
- [ ] 3rd Review
- [ ] 4th Review
- [ ] 5th Review