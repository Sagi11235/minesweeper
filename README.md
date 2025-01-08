# minesweeper
function that get minesweeper solution and design the board
def minesweeper_numbers(board):
    ans = [[0 for col in range(len(board[0][:]))] for row in range(len(board[:][0]))]
    for i in range(0,len(board[0][:])):
        for j in range(0,len(board[:][i])):
            if board[j][i]==1:
                ans[j][i]=9
            else:
                if j!=0:
                    ans[j][i]=ans[j][i]+board[j-1][i]
                if j!=len(board[:][i])-1:
                    ans[j][i]=ans[j][i]+board[j+1][i]
                if i!=0:
                    ans[j][i]=ans[j][i]+board[j][i-1]
                if i!=len(board[0][:])-1:
                    ans[j][i]=ans[j][i]+board[j][i+1]
                if j!=0 and i!=0:
                    ans[j][i]=ans[j][i]+board[j-1][i-1]
                if j!=0 and i!=len(board[0][:])-1:
                    ans[j][i]=ans[j][i]+board[j-1][i+1]
                if j!=len(board[:][i])-1 and i!=0:
                    ans[j][i]=ans[j][i]+board[j+1][i-1]
                if j!=len(board[:][i])-1 and i!=len(board[0][:])-1:
                    ans[j][i]=ans[j][i]+board[j+1][i+1]
    return ans

print(minesweeper_numbers([
  [1, 1, 0, 0, 0, 0, 0, 0],
  [1, 1, 0, 0, 0, 0, 0, 0],
  [0, 0, 0, 0, 0, 0, 1, 0],
  [1, 1, 0, 0, 0, 0, 0, 0],
  [0, 0, 0, 1, 1, 1, 1, 0],
  [0, 1, 0, 0, 0, 0, 1, 1],
  [1, 0, 0, 0, 1, 0, 0, 0],
  [0, 0, 1, 0, 1, 0, 1, 1],
]))
