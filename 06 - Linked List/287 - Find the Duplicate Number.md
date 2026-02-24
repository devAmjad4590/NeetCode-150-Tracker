
# [Find the Duplicate Number]

- **Problem Number**: 287
- **Difficulty**: Medium (should be Hard)
- **Pattern**: Linked list + Floyd's algorithm

---

### Key Insight

- O(n) time complexity
- O(1) memory (restriction rule)
- We use the value of the array as the Node value, and take the index of that value as a pointer to the next Node. The screenshot below demonstrates such
- ![[Pasted image 20260224090925.png]]
- After going the slow and fast pointer intersect, we break the loop. And initialize a second slow pointer, and move it to the next along with the first slow pointer. And eventually, they will meet. The cycle'd value is essentially the duplicate number. Either we find it in an easy 1 to 1 cycle or there can be a long looped cycle. The easy to find to cycle is easy to find. But the long looped is what made the floyd's algorithm flourish and detect the duplication number

---

### Solution

```python
class Solution:
    def findDuplicate(self, nums: List[int]) -> int:
        slow, fast = 0, 0
        while True:
            slow = nums[slow]
            fast = nums[nums[fast]]
            if slow == fast:
                break
                
        slow2 = 0
        while True:
            slow = nums[slow]
            slow2 = nums[slow2]
            if slow == slow2:
                return slow
```

---

### Spaced Repetition

- **Next Review Date**: 2026-02-25
- **Review Log**:
    - 2026-02-24 - Solved
    - YYYY-MM-DD - Reviewed

### Review Reptitions
- [ ] 1st Review
- [ ] 2nd Review
- [ ] 3rd Review
- [ ] 4th Review
- [ ] 5th Review




