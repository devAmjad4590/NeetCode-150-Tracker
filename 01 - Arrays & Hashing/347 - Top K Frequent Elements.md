
# [Top K Frequent Elements]

- **Problem Number**: 347
- **Difficulty**: Medium
- **Pattern**: Bucket Sort

---

### Key Insight

- O(n) for time complexity. O(n) for space
- So we start with a map to store the values and how much count for each. After that, we need to initialize a freq array that starts with this structure `[[],[],[],[],[]]` + 1 of the total size of num array. We store the counts of the numbers as the index in the freq array. And the values within it to be the actual numbers. So in this bucketsort solution, the index is the count of the numbers and the values in these indices are the actual values. 

---

### Solution

```python
class Solution:
    def topKFrequent(self, nums: List[int], k: int) -> List[int]:
        count = {}
        freq = [[] for i in range(len(nums) + 1)]
        # [[], [], [], [7], [], [6]]
        for i in nums:
            count[i] = 1 + count.get(i, 0)
        for key,val in count.items():
            freq[val].append(key)
        res = []
        for i in range(len(freq) - 1, 0, -1):
            for n in freq[i]:
                res.append(n)
            if len(res) == k:
                return res
        return []
```

---

### Spaced Repetition

- **Next Review Date**: 2026-02-02
- **Review Log**:
    - 2025-11-04 - Solved
    - 2026-01-29 - Reviewed
### Review Reptitions
- [x] 1st Review
- [ ] 2nd Review
- [ ] 3rd Review
- [ ] 4th Review
- [ ] 5th Review