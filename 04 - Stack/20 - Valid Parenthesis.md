
# [20 - Valid Parenthesis]

- **Problem Number**: Easy
- **Difficulty**: 20
- **Pattern**: Stack

---

### Key Insight

- O(n) time complexitiy
- O(n) space
- We append all the opening brackets. If it is closing, we start popping and check if the top of the stack is equal to the opening bracket of that character. If true then its valid so far, if not then return False

---

### Solution

```python
class Solution:
    def isValid(self, s: str) -> bool:
        map = {
          '}': '{',
          ')': '(',
          ']': '['
        }
        stack = []
  

        for i in s:
          if i in map:
            if stack and stack[-1] == map[i]:
              stack.pop()
            else:
              return False
          else:
            stack.append(i)
        if not stack:
          return True
        else:
          return False
```

---

### Spaced Repetition

- **Next Review Date**: 2026-04-24
- **Review Log**:
    - 2025-11-01 - Solved
    - 2026-04-23 - Reviewed

### Review Reptitions
- [x] 1st Review
- [x] 2nd Review
- [ ] 3rd Review
- [ ] 4th Review
- [ ] 5th Review