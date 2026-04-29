
# [Problem Name]

- **Problem Number**: 74
- **Difficulty**: Medium
- **Pattern**: Binary Search

---

### Key Insight

- O(log m * log n) where m is number of rows and n is the number of columns
- So we perform binary search both on the 2d level and then on the array that has the target value by comparing the target with the last element of the matrix on the 2d level. We compare if the target is greater than the last value of that array. If it is greater than for sure its not on the level. If it is less, then it is for sure somewhere on the array. I also added another condition with the first part of the array.

---

### Solution

```python
class Solution:
    def searchMatrix(self, matrix: List[List[int]], target: int) -> bool:
        l = 0
        r = len(matrix) - 1
        nums = matrix
        while l <= r:
            m = l + ((r - l) // 2)
            if nums[m][-1] == target:
                return True
            elif nums[m][0] < target and nums[m][-1] < target:
                l = m + 1
            elif nums[m][0] > target and nums[m][-1] > target:
                r = m - 1
            else:
                return self.binarySearch(nums[m], target)
        return False

  

    def binarySearch(self, nums, target):
        l = 0
        r = len(nums) - 1
        while l <= r:
            m = l + ((r - l) // 2)
            if nums[m] == target:
                return True
            elif nums[m] < target:
                l = m + 1
            else:
                r = m - 1
        return False
```

---

### Spaced Repetition

- **Next Review Date**: 2026-04-29
- **Review Log**:
    - 2026-04-28 - Solved
    - YYYY-MM-DD - Reviewed

### Review Reptitions
- [ ] 1st Review
- [ ] 2nd Review
- [ ] 3rd Review
- [ ] 4th Review
- [ ] 5th Review