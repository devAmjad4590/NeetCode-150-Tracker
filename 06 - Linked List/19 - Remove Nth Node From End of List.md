
# [Problem Name]

- **Problem Number**: 19
- **Difficulty**: Medium
- **Pattern**: Two pointers with Iteration to count the steps

---

### Key Insight

- O(n) time complexity
- O(1) Memory
- First we count the length of the linked list, then simply find the Nth node by using the formula `Steps = Length - n`. We iterate to that node with the help of two pointers. Prev and Curr. Prev is the pointer that is positioned before the Nth node so that we can manipulate the pointers to the node next to the Nth Node.
- Edge case of `[1,2]` can be dealt with if the numbers of `steps == 0`, simply return `head.next`.

---

### Solution

```python
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, val=0, next=None):
#         self.val = val
#         self.next = next
  

class Solution:
    def removeNthFromEnd(self, head: Optional[ListNode], n: int) -> Optional[ListNode]:
        if not head:
            return None
        if not head.next:
            return None
  

        count = head
        length = 0
        while count:
            count = count.next
            length += 1
        steps = length - n
        curr = head
        prev = None

        if steps == 0:
            return head.next
  

        for i in range(steps):
            prev = curr
            curr = curr.next
        prev.next = curr.next
        curr.next = None
        return head
```

---

### Spaced Repetition

- **Next Review Date**: 2026-03-22
- **Review Log**:
    - 2026-02-10 - Solved
    - 2026-03-15 - Reviewed

### Review Reptitions
- [x] 1st Review
- [x] 2nd Review
- [ ] 3rd Review
- [ ] 4th Review
- [ ] 5th Review