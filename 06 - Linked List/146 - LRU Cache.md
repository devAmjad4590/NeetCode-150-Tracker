# [LRU Cache]

- **Problem Number**: 146
- **Difficulty**: Medium
- **Pattern**: Hashmap & Doubly Linked list

---

### Key Insight

- O(n) space
- O(1) operations `get` and `put`
- The operations in this LRU Cache class uses put and get as O(1) operations. However, the challenge was to deal with the ordering of memory. HashMap does not help us to make the ordering of the memory easy to reallocate. Therefore, the linkedlist was a solution to that. 
- We store the Keys in a map and the Nodes as a value to these keys. Where we insert two dummy nodes representing the Least Recently Used Key/Node and Mos trecently Used Key/Node. Doubly linked list makes it easy to speed up the operations to O(1) as well.
- Pretty cool dynamics ig, learnt a lot here

---

### Solution

```python
class Node:
    def __init__(self, key, val):
        self.key = key
        self.val = val
        self.prev, self.next = None, None


class LRUCache:
  

    def __init__(self, capacity: int):
        self.capacity = capacity
        self.cache = {}
        # Left = LRU, Right = MRU
        self.left, self.right = Node(0, 0), Node(0, 0)
        self.left.next = self.right
        self.right.prev = self.left

    def remove(self, node):
        prev = node.prev
        next = node.next
  

        prev.next = next
        next.prev = prev

        node.next = node.prev = None

    def insert(self, node):
        prev = self.right.prev
        next = self.right
        prev.next = node
        next.prev = node

        node.next = next
        node.prev = prev

    def get(self, key: int) -> int:
        if key in self.cache:
            # we remove and insert it so that it is placed to the RIGHT SIDE (MRU)
            self.remove(self.cache[key])
            self.insert(self.cache[key])
            return self.cache[key].val
        return -1

    def put(self, key: int, value: int) -> None:
        if key in self.cache:
            self.remove(self.cache[key])
        self.cache[key] = Node(key, value) # its overwriting incase the key alrdy exists, or just adding it if it doesnt. it handles both cases
        self.insert(self.cache[key])

        if len(self.cache) > self.capacity:
            lru = self.left.next
            self.remove(lru)
            del self.cache[lru.key]
```

---

### Spaced Repetition

- **Next Review Date**: 2026-04-25
- **Review Log**:
    - 2026-04-09 - Solved
    - 2026-04-18 - Reviewed

### Review Reptitions
- [x] 1st Review
- [x] 2nd Review
- [ ] 3rd Review
- [ ] 4th Review
- [ ] 5th Review