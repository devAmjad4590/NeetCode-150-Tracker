
# [Valid Sudoku]

- **Problem Number**: 36
- **Difficulty**: Medium
- **Pattern**: HashMap & Set

---

### Key Insight

- Time complexity kinda constant i think? cuz you only loop 18 times for this problem
- You check for each row, each column and each square.
- Tried to do it with using a regular array solution but using hashmap and set is the easiest approach.
- For the squares, you kinda have to think literally out of the box. Like zoom out kinda and store the keys using the formula `i//3, j//3` 

---

### Solution

```python
class Solution:
    def isValidSudoku(self, board: List[List[str]]) -> bool:
        row = defaultdict(set) # key : value (set)
        col = defaultdict(set)
        square = defaultdict(set)

  
        for i in range(9):
            for j in range(9):
                if board[i][j] == ".":
                    continue
                val = board[i][j]

                if val in row[j] or val in col[i] or val in square[(i // 3, j // 3)]:
                    return False
                row[j].add(val)
                col[i].add(val)
                square[(i//3, j//3)].add(val)
        return True
```

---

### Spaced Repetition

- **Next Review Date**: 2026-04-02
- **Review Log**:
    - 2026-12-19 - Solved
    - 2026-04-01 - Reviewed

### Review Reptitions
- [ ] 1st Review
- [ ] 2nd Review
- [ ] 3rd Review
- [ ] 4th Review
- [ ] 5th Review