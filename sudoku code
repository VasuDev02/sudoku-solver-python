import numpy as np
def get_empty(puzzle):
    for i in range(9):
        for j in range(9):
            if puzzle[i][j]==0:
                return i,j
    return None,None

def valid_guess(puzzle,guess,row,col):
    r_vals=puzzle[row]
    if guess in r_vals:
        return False
    c_vals=[]
    for i in range(9):
        c_vals.append(puzzle[i][col])
    if guess in c_vals:
        return False
    r_start=(row//3)*3
    c_start=(col//3)*3
    for i in range(r_start,r_start+3):
        for j in range(c_start,c_start+3):
            if guess==puzzle[i][j]:
                return False
    return True

def sudokusolve(puzzle):
    row,col=get_empty(puzzle)
    if row is None:
        return True
    for guess in range(1,10):
        if valid_guess(puzzle,guess,row,col):
            puzzle[row][col]=guess
            if sudokusolve(puzzle):
                return True
        puzzle[row][col]=0
    return False

if __name__ == '__main__':
    example_board = np.array([
        [1, 0, 6,   4, 0, 0,   0, 0, 7],
        [4, 0, 0,   0, 0, 7,   0, 0, 0],
        [0, 0, 8,   9, 2, 0,   0, 4, 6],

        [0, 6, 0,   1, 0, 4,   0, 0, 0],
        [0, 8, 1,   0, 0, 0,   0, 3, 0],
        [2, 0, 0,   8, 0, 5,   6, 0, 1],

        [0, 0, 0,   0, 0, 0,   0, 0, 0],
        [0, 3, 4,   0, 6, 0,   7, 0, 0],
        [0, 1, 7,   0, 0, 0,   9, 6, 0]
    ])
    print(sudokusolve(example_board))
    reshape=np.reshape(example_board,(9,9))
    print(reshape)
