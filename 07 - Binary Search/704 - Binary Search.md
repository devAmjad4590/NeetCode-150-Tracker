
# [Binary Search]

- **Problem Number**: 704
- **Difficulty**: Easy
- **Pattern**: Binary Search

---

### Key Insight

- O(log n) speed
- O(1) space
- left and right pointers that changes based on the calculated mid value if it is greater or less than the target value. If target is greater than mid, then it means the target is somewhere on the right side, so we dismiss everything on the left side of that mid. Moving the left pointer. Vice versa for the right pointer

---

### Solution

```python
class Solution:
    def search(self, nums: List[int], target: int) -> int:
        left = 0
        right = len(nums) - 1
        while left <= right:
            # mid = (left + right) // 2
            mid = left + ((right - left) // 2) # to avoid overflow
            if nums[mid] == target:
                return mid
            elif target > nums[mid]:
                left = mid + 1
            else:
                right = mid - 1
        return -1
```

---

### Spaced Repetition

- **Next Review Date**: 2026-04-26
- **Review Log**:
    - 2026-04-22 - Solved
    - 2026-04-23 - Reviewed

### Review Reptitions
- [x] 1st Review
- [ ] 2nd Review
- [ ] 3rd Review
- [ ] 4th Review
- [ ] 5th Review