# [Longest Consecutive Sequence]

- **Problem Number**: 128
- **Difficulty**: Medium
- **Pattern**: Set

---

### Key Insight

- O(n) time complexity and space
- You start to store the array in a set, then figure out a potential beginning sequence by checking if this number has a previous value `n-1`. If it does, its part of a sequence so we skip those for now. If it isn't, then its a potentially a beginning of a sequnce.
- After determining the beginning of a sequence, we simply check if the number after it exists or not in the set using `length` as the incrementer as well as the variable that determines the length of that sequence. `if (num + length) in set: length += 1`. 
- Then we conclude by picking the maximum length sequence. `longest = max(longest, length)`. There can be multiple long sequences but we only care about the longest one.

---

### Solution

```python
class Solution:
    def longestConsecutive(self, nums: List[int]) -> int:
        numSet = set(nums)
        longest = 0


        for num in numSet:
            if (num-1) not in numSet:
                length = 1
                while (num + length) in numSet:
                    length += 1
                longest = max(longest, length)
        return longest
```

---

### Spaced Repetition

- **Next Review Date**: 2026-04-29
- **Review Log**:
    - 2025-12-20 - Solved
    - 2026-04-22 - Reviewed

### Review Reptitions
- [x] 1st Review
- [x] 2nd Review
- [ ] 3rd Review
- [ ] 4th Review
- [ ] 5th Review