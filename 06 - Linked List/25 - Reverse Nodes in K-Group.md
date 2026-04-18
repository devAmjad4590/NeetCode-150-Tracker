
# [Reverse Nodes in K-Group]

- **Problem Number**: 25
- **Difficulty**: Hard
- **Pattern**: Linked List

---

### Key Insight

- O(n) time complexity
- O(1) space
- So we use two points to track the previous group and the next group. And then with that we start to find the kth node. and reverse the linked list with setting the prev node to the groupNext node because we wanna make sure the last node after reverse is set at the kth node. 
- And then we update the pointers .next according to the reversed linked list. very cool problem to solve

---

### Solution

```python
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, val=0, next=None):
#         self.val = val
#         self.next = next


class Solution:
     def reverseKGroup(self, head: Optional[ListNode], k: int) -> Optional[ListNode]:
          dummy = ListNode(0, head)
          groupPrev = dummy
          while True:
               kth = self.getKthNode(groupPrev, k)
               if not kth:
                    break
               groupNext = kth.next
               curr = groupPrev.next
               prev = groupNext
               while curr != groupNext:
                    after = curr.next
                    curr.next = prev
                    prev = curr
                    curr = after
               tmp = groupPrev.next
               groupPrev.next = kth
               groupPrev = tmp
          return dummy.next

  
     def getKthNode(self, head, k):
          while head and k > 0:
             head = head.next
             k -= 1
          return head
```

---

### Spaced Repetition

- **Next Review Date**: 2026-04-21
- **Review Log**:
    - 2026-04-14 - Solved
    - 2026-04-18 - Reviewed

### Review Reptitions
- [x] 1st Review
- [ ] 2nd Review
- [ ] 3rd Review
- [ ] 4th Review
- [ ] 5th Review