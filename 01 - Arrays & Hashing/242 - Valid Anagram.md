
# [Valid Anagram]

- **Problem Number**:  242
- **Difficulty**: Easy
- **Pattern**: Sort

---

### Key Insight

- Sort them both and return the comparison operator result

---

### Solution

```python
class Solution:
    def isAnagram(self, s: str, t: str) -> bool:
        return sorted(s) == sorted(t)
```

---

### Spaced Repetition

- **Next Review Date**: 2026-01-29
- **Review Log**:
    - 2025-10-29 - Solved
    - 2026-01-26 - Reviewed
### Review Reptitions
- [x] 1st Review
- [ ] 2nd Review
- [ ] 3rd Review
- [ ] 4th Review
- [ ] 5th Review