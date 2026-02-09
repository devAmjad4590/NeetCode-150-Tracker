# [Linked List Cycle]

- **Problem Number**: 141
- **Difficulty**: Easy
- **Pattern**: Two pointers (Slow and fast)

---

### Key Insight

- O(n) time complexity and O(1) memory
- Simply have two pointers, one that is iterating normally and the other iterating two steps ahead. If a cycle was there, the two pointers will meet then return True. Else False.

---

### Solution

```python
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, val=0, next=None):
#         self.val = val
#         self.next = next
class Solution:
    def hasCycle(self, head: Optional[ListNode]) -> bool:
        slow = head
        fast = head
        while fast and fast.next:
            slow = slow.next
            fast = fast.next.next
            if slow == fast:
                return True
        return False
```

---

### Spaced Repetition

- **Next Review Date**: 2026-02-16
- **Review Log**:
    - 2026-02-01 - Solved
    - 2026-02-09 - Reviewed

### Review Reptitions
- [x] 1st Review
- [x] 2nd Review
- [ ] 3rd Review
- [ ] 4th Review
- [ ] 5th Review