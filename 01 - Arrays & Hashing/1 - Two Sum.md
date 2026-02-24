
# [Two Sum]

- **Problem Number**: 1
- **Difficulty**: Easy
- **Pattern**: HashMap

---

### Key Insight

- O(n) time complexity
- Use a hashmap to store the diff of the target and num[i] as key, then store the index as value.
- Formula: Diff = Target - num[i]

---

### Solution

```python
class Solution:
    def twoSum(self, nums: List[int], target: int) -> List[int]:
        map = {}
        for i in range(len(nums)):
            x = target - nums[i]
            if x in map:
                return [map[x], i]
            map[nums[i]] = i
        return []
```

---

### Spaced Repetition

- **Next Review Date**: 2026-03-10
- **Review Log**:
    - 2025-10-30 - Solved
    - 2026-02-24 - Reviewed

### Review Reptitions
- [x] 1st Review
- [x] 2nd Review
- [x] 3rd Review
- [ ] 4th Review
- [ ] 5th Review