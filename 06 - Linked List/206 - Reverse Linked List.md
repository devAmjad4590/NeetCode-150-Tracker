
# [Reverse Linked List]

- **Problem Number**:  206
- **Difficulty**: Easy
- **Pattern**: Two Pointers (More like three tbh)

---

### Key Insight

- It is an O(n) time complexity solution with O(1) memory.
- Three pointers work together to reverse the array and also iterating throughout the linked list. Curr (starts at the Head), Before (starts as None), and After (The node after the Head).
	- First you initialize the After node in the loop (`after = curr.next`)
	- Then you point the Curr's next pointer to Before Node.
	- Then move the Before to the Curr
	- Then move the Curr to the After
	- The loop breaks when Curr is None

---

### Solution

```python
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, val=0, next=None):
#         self.val = val
#         self.next = next
class Solution:
    def reverseList(self, head: Optional[ListNode]) -> Optional[ListNode]:
        if head is None:
            return None
        curr = head
        before = None
        while curr:
            after = curr.next
            curr.next = before
            before = curr
            curr = after
        head = before
        return head
```

---

### Spaced Repetition

- **Next Review Date**: 2026-02-08
- **Review Log**:
    - 2026-01-25 - Solved
    - 2026-02-01 - Reviewed
### Review Reptitions
- [x] 1st Review
- [x] 2nd Review
- [ ] 3rd Review
- [ ] 4th Review
- [ ] 5th Review