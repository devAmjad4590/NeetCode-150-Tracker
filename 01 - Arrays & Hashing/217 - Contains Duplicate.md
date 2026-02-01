
# [Contains Duplicate]

- **Problem Number**: 217
- **Difficulty**: Easy
- **Pattern**: Set

---

### Key Insight

- O(n) time complexity
- Using a set, if it exists in the set then return True. Else return False

---

### Solution

```python
class Solution:
    def hasDuplicate(self, nums: List[int]) -> bool:
        seen = set()
        for i in nums:
            if i in seen:
                return True
            seen.add(i)
        return False
```

---

### Spaced Repetition

- **Next Review Date**: 2026-02-08
- **Review Log**:
    - 2025-10-29 - Solved
    - 2026-02-01 - Reviewed
### Review Reptitions
- [x] 1st Review
- [x] 2nd Review
- [ ] 3rd Review
- [ ] 4th Review
- [ ] 5th Review