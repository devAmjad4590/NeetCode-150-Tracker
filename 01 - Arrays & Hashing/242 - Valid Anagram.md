# [Valid Anagram]

- **Problem Number**:  242
- **Difficulty**: Easy
- **Pattern**: Sort, Hashmap

---

### Key Insight

- Sort them both and return the comparison operator result

---

### Solution

```python
class Solution:
    def isAnagram(self, s: str, t: str) -> bool:
        if len(s) != len(t):
            return False
        countS, countT = {}, {}
        for i in range(len(s)):
            countS[s[i]] = 1 + countS.get(s[i], 0)
            countT[t[i]] = 1 + countT.get(t[i], 0)
        return countS == countT
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