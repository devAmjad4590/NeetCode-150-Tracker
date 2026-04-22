# [Merge K Sorted Linked Lists]

- **Problem Number**: 23
- **Difficulty**: Hard
- **Pattern**: LinkedList, Merge Linked List, Sorting Algorithm

---

### Key Insight

- time complexity O(n log k) , where k is number of lists
- memory complexity O(k)
- We iterate through the array of linked lists and sort each two linked lists. If odd, we sort one linked list and leave the other as None.
- After selecting two linked list, we sort them using the merge List algorithm and append that merged sorted linked list into the temp arry `mergedLists`. Then we update the `lists` and check if the length is > 1. If it is then there is more merging to do, if not then return `lists[0]`

---

### Solution

```python
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, val=0, next=None):
#         self.val = val
#         self.next = next


class Solution:    
    def mergeKLists(self, lists: List[Optional[ListNode]]) -> Optional[ListNode]:
        if not lists or len(lists) == 0:
                return None
        while len(lists) > 1:
                mergedLists = []
                for i in range(0, len(lists), 2):
                        l1 = lists[i]
                        l2 = lists[i+1] if (i+1) < len(lists) else None
                        mergedLists.append(self.mergeList(l1, l2))
                lists = mergedLists
        return lists[0]


    def mergeList(self, l1, l2):
        dummy = ListNode(0)
        tail = dummy

        while l1 and l2:
                if l1.val < l2.val:
                        tail.next = l1
                        l1 = l1.next
                else:
                        tail.next = l2
                        l2 = l2.next
                tail = tail.next
        if l1:
                tail.next = l1
        if l2:
                tail.next = l2
        return dummy.next
```

---

### Spaced Repetition

- **Next Review Date**: 2026-04-29
- **Review Log**:
    - 2026-04-12 - Solved
    - 2026-04-22 - Reviewed

### Review Reptitions
- [x] 1st Review
- [x] 2nd Review
- [ ] 3rd Review
- [ ] 4th Review
- [ ] 5th Review