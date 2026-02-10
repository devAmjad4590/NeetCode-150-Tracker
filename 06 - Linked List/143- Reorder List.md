# [Reorder List]

- **Problem Number**: 143
- **Difficulty**: Medium
- **Pattern**: Reverse & Two Pointers & Merge

---

### Key Insight

- O(n) time complexity
- To solve this problem, we first split the list into two parts. And the way we split it is by using the slow and fast pointers where slow is initialised at the head and slow is initailised next to the head. Make sure to detach the first half from the second half (`slow.next = None`)
- Second, we reverse the second half list using the reverse method we learned from [[206 - Reverse Linked List]].
- Third, we finally merge them. We use temp variables to store the .next for the first head and the second head. Then we iterate until the second head to be None (As sometimes if the linkedlist was odd, the second list head would be None before the first list).

---

### Solution

```python
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, val=0, next=None):
#         self.val = val
#         self.next = next
class Solution:
    def reorderList(self, head: Optional[ListNode]) -> None:
        # split the list
        slow = head
        fast = head.next
        while fast and fast.next:
            slow = slow.next
            fast = fast.next.next
        second = slow.next
        slow.next = None # to detach the first half from the second
        
        # reverse the second half
        prev = None # new head of the reversed second half
        while second:
            after = second.next
            second.next = prev
            prev = second
            second = after
            
        # merge first and second list
        first = head
        second = prev
        while second:
            tmp1, tmp2 = first.next, second.next
            first.next = second
            second.next = tmp1
            first = tmp1
            second = tmp2
```

---

### Spaced Repetition

- **Next Review Date**: 2026-02-13
- **Review Log**:
    - 2026-02-09 - Solved
    - 2026-02-11 - Reviewed

### Review Reptitions
- [x] 1st Review
- [ ] 2nd Review
- [ ] 3rd Review
- [ ] 4th Review
- [ ] 5th Review