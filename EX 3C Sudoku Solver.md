# EX 3C Sudoku Solver
## DATE:
## AIM:
To write a python program to find the solution of sudoku puzzle using Backtracking.


## Algorithm
1.Scan the board to find an empty cell (with value 0).
2.For the empty cell, try placing numbers 1 to 9.
3.Use isPossible() to check if placing a number follows Sudoku rules (row, column, 3×3 box).
4.Place the number and recursively attempt to solve the rest of the board.
5.If stuck, backtrack by resetting the cell to 0 and trying the next number.


```
/*
Program to implement to to find the solution of sudoku puzzle using Backtracking.
Developed by: jayaseelan
Register Number:  212223220039
*/
```
## Program:
```
board = [
    [0, 0, 0, 8, 0, 0, 4, 0, 3],
    [2, 0, 0, 0, 0, 4, 8, 9, 0],
    [0, 9, 0, 0, 0, 0, 0, 0, 2],
    [0, 0, 0, 0, 2, 9, 0, 1, 0],
    [0, 0, 0, 0, 0, 0, 0, 0, 0],
    [0, 7, 0, 6, 5, 0, 0, 0, 0],
    [9, 0, 0, 0, 0, 0, 0, 8, 0],
    [0, 6, 2, 7, 0, 0, 0, 0, 1],
    [4, 0, 3, 0, 0, 6, 0, 0, 0]
]

def printBoard(board):
    for i in range(0, 9):
        for j in range(0, 9):
            print(board[i][j], end=" ")
        print()

def isPossible(board, row, col, val):
    for j in range(0, 9):
        if board[row][j] == val:
            return False

    for i in range(0, 9):
        if board[i][col] == val:
            return False

    startRow = (row // 3) * 3
    startCol = (col // 3) * 3
    for i in range(0, 3):
        for j in range(0, 3):
            if board[startRow+i][startCol+j] == val:
                return False
    return True

def solve():
    for i in range(9):
        for j in range(9):
            if board[i][j]==0:
                for n in range(1,10):
                    if isPossible(board,i,j,n):
                        board[i][j]=n
                        if solve():
                            return True
                        board[i][j]=0
                return False
    return True
if solve():
    printBoard(board)
```


## Output:
![437673796-5f80b1b4-aa60-4072-baca-42245176454a](https://github.com/user-attachments/assets/877f0c4e-5162-41aa-a05e-b7e4f4d2f02d)



## Result:
The Sudoku solver program executed successfully and found the solution for the given puzzle.
