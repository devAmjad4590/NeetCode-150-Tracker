
# [Product of Array Except Self]

- **Problem Number**: 238
- **Difficulty**: Medium
- **Pattern**: Prefix & Postfix Array

---

### Key Insight

- O(n) time complexity
- O(1) memory (output don't count)
- We use prefix to calculate from left to right, this represents the product except self as we iterating through the array. For example, if i = 3 in nums[i], then we know in the prefix array at position i - 1, will be the multiplication of all the values from the left side.
- Similarly, we do the same for postfix, it will calculate the values of multiplication from the right side. 
- The way we solve it with O(1) without using arrays for prefix and postfix, we fill up the res array with prefix results, and simply append the multiplication of the postfix to the res array that was already filled up with the prefix. 

---

### Solution

```python
class Solution:
    def productExceptSelf(self, nums: List[int]) -> List[int]:
        prefix = 1
        res = [1] * len(nums)
        for i in range(len(nums)):
            res[i] = prefix
            prefix *= nums[i]
            
        postfix = 1
        for i in range(len(nums)-1, -1 , -1):
            res[i] *= postfix
            postfix *= nums[i]
        return res
```

---

### Spaced Repetition

- **Next Review Date**: 2026-04-30
- **Review Log**:
    - 2026-11-05 - Solved
    - 2026-03-23 - Reviewed

### Review Reptitions
- [x] 1st Review
- [x] 2nd Review
- [ ] 3rd Review
- [ ] 4th Review
- [ ] 5th Review