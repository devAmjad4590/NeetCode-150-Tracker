# [Group Anagram]

- **Problem Number**: 49
- **Difficulty**: Medium
- **Pattern**: HashMap

---

### Key Insight

- O(m * n)
- Sorting is at best O(n log n)., which forces the solution to be O(m * nlogn), where m is the numbers of words and n log n is the sorting of these words. We can sort out the string and store them as keys in a dict. Then just simply append the array of strings as values assigning to their sorted keys. But can we improve that?
- Best efficient way to solve this problem, is we count the amount of letters within that string and store them as keys. For example, "eat" and "ate" should belong to the same key. We count the letters as such (1e 1a 1t). And store that as their keys and simply append them. To accomplish that, we initialize an array of 0's with size 26 to represent the letters `count = [0] * 26`. We find their asci values using `ord()` and subtract it with `ord('a')` to get their alphabetical positions. And we increment their values in the count array. And return the `map.values()`

---

### Solution

```python
    def groupAnagrams(self, strs: List[str]) -> List[List[str]]:
        res = defaultdict(list) # defaultdict to avoid edgecases like map init empty
        for s in strs:
            count = [0] * 26
            for c in s:
                count[ord(c) - ord("a")] += 1
                # doesn't matter what value is ord(c) as long as we subtract it
                # from the start of the alphabet.
                # if 'a' was 80 and c was '90', then 90 - 80 = 10, which is 'j'  
            res[tuple(count)].append(s) # tuple because list is immutable.
            # so we use tuple to add a list as key.
        return list(res.values())
```

---

### Spaced Repetition

- **Next Review Date**: 2026-02-16
- **Review Log**:
    - 2026-01-29 - Solved
    - 2026-02-09 - Reviewed

### Review Reptitions
- [x] 1st Review
- [x] 2nd Review
- [ ] 3rd Review
- [ ] 4th Review
- [ ] 5th Review