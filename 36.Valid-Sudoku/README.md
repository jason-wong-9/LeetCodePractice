#36. Valid Sudoku
Determine if Sudoku is valid.
```java
public boolean isValidSudoku(char[][] board) {
    Set seen = new HashSet();
    for (int i = 0; i < 9; ++i){
        for (int j = 0; j < 9; ++j){
            char number = board[i][j];
            if (number != '.'){
                // When an item is already in the set, it would return false when trying to add.
                if (!seen.add(number + " in row " + i) ||
                    !seen.add(number + " in column " + j) ||
                    !seen.add(number + " in block " + i/3 + "-" + j/3))
                    return false;
            }
        }
    }
    return true;
}
```
