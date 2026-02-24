
# [Add Two Numbers]

- **Problem Number**: 2
- **Difficulty**: Medium
- **Pattern**: Linked List

---

### Key Insight

- O(m + n) time complexity
- O(1) memory
- Using the good old addition method that we learned from school.
- Value is calculated by % of 10 (if there was a remainder, we only insert one digit and move the carry over to the next digit).
- carry is calculated by doing the formula `val // 10`. 

---

### Solution

```python
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, val=0, next=None):
#         self.val = val
#         self.next = next

  
class Solution:
    def addTwoNumbers(self, l1: Optional[ListNode], l2: Optional[ListNode]) -> Optional[ListNode]:
        dummy = ListNode(0)
        head = dummy
        carry = 0
        while l1 or l2 or carry:
            v1 = l1.val if l1 else 0
            v2 = l2.val if l2 else 0
  

            val = v1 + v2 + carry
            carry = val // 10
            val = val % 10
            dummy.next = ListNode(val)
  

            l1 = l1.next if l1 else None
            l2 = l2.next if l2 else None
            dummy = dummy.next
        return head.next
```

---

### Spaced Repetition

- **Next Review Date**: 2026-02-27
- **Review Log**:
    - 2026-02-23 - Solved
    - 2026-02-24 - Reviewed

### Review Reptitions
- [x] 1st Review
- [ ] 2nd Review
- [ ] 3rd Review
- [ ] 4th Review
- [ ] 5th Review