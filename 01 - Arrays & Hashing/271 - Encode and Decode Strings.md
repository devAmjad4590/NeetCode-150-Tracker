
# [Encode and Decode Strings]

- **Problem Number**: 271
- **Difficulty**: Medium
- **Pattern**: Array

---

### Key Insight

- O(m) for each encode and decode function
- O(m + n) for each encode and decode function
- We encode the string by storing its length first, following up with a '#' to highlight where the word starts as well as the end of the length. Then iterate using the length we stripped from the string. For example, `4#neet4#code`. 
- In decode, we iterate through the string word, we strip the length of the word before the '#'. Then using that length we stripped, we are able to strip the word and move the pointer to the next number using `j+1 + length` (the letter after the '#' plus the length of the word). With that number, we can decode the next word. 

---

### Solution

```python
class Solution:
    def encode(self, strs: List[str]) -> str:
        res = ""
        for s in strs:
            length = len(s)
            res += str(length) + '#' + s
        return res

    def decode(self, s: str) -> List[str]:
        res = []
        i = 0
        while i != len(s):
            j = i
            while s[j] != '#':
                j += 1
            length = int(s[i:j])
            word = s[j+1 : j + 1 + length]
            res.append(word)
            i = j + 1 + length
        return res
```

---

### Spaced Repetition

- **Next Review Date**: 2026-03-22
- **Review Log**:
    - 2026-12-03 - Solved
    - 2026-03-15 - Reviewed

### Review Reptitions
- [x] 1st Review
- [x] 2nd Review
- [ ] 3rd Review
- [ ] 4th Review
- [ ] 5th Review