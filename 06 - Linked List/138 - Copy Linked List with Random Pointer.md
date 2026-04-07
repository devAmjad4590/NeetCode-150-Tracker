
# [Copy Linked List with Random Pointer]

- **Problem Number**: 138
- **Difficulty**: Medium
- **Pattern**: Hash Map & Linked List

---

### Key Insight

- Two Pass approach, one to create the new nodes without the .next and .random assigned. As well as making the old node be the key and the new node be the values. Second pass, is finally assigned the new nodes to the .next and .random using the value of the old nodes in the hashmap. pretty cool
- ![[Pasted image 20260406093337.png]]

---

### Solution

```python
class Solution:
    def copyRandomList(self, head: 'Optional[Node]') -> 'Optional[Node]':
        if head is None:
            return None
        linkMap = defaultdict(Node)
        curr = head
        while curr:
            linkMap[curr] = Node(curr.val, None, None)
            curr = curr.next

        for key, value in linkMap.items():
            node = value
            old_node = key
            value.next = linkMap.get(old_node.next)
            value.random = linkMap.get(old_node.random)
        return next(iter(linkMap.values())) # return first element O(1)
```

---

### Spaced Repetition

- **Next Review Date**: 2026-04-10
- **Review Log**:
    - 2026-04-06 - Solved
    - 2026-04-07 - Reviewed

### Review Reptitions
- [x] 1st Review
- [ ] 2nd Review
- [ ] 3rd Review
- [ ] 4th Review
- [ ] 5th Review