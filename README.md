<h1>ExpNo 7 : Implement Alpha-beta pruning of Minimax Search Algorithm for a Simple TIC-TAC-TOE game</h1> 
<h3>Name: Dhanush G     </h3>
<h3>Register Number:2305002006        </h3>
<H3>Aim:</H3>
<p>
Implement Alpha-beta pruning of Minimax Search Algorithm for a Simple TIC-TAC-TOE game
</p>
<h1>GOALS of Alpha-Beta Pruning in MiniMax Search Algorithm</h1>

<h3>Improve the decision-making efficiency of the computer player by reducing the number of evaluated nodes in the game tree.</h3>
<h3>Tic-Tac-Toe game implementation incorporating the Alpha-Beta pruning and the Minimax algorithm with Python Code.</h3>
<h1>IMPLEMENTATION</h1>

The project involves developing a Tic-Tac-Toe game implementation incorporating the Alpha-Beta pruning with the Minimax algorithm. Using this algorithm, the computer player analyzes the game state, evaluates possible moves, and selects the optimal action based on the anticipated outcomes.

<h1>The Minimax algorithm</h1>

recursively evaluates all possible moves and their potential outcomes, creating a game tree.

<h1>Alpha-Beta pruning</h1>

Alpha–Beta (𝛼−𝛽) algorithm is actually an improved minimax using a heuristic. It stops evaluating a move when it makes sure that it’s worse than a previously examined move. Such moves need not to be evaluated further.

When added to a simple minimax algorithm, it gives the same output but cuts off certain branches that can’t possibly affect the final decision — dramatically improving the performance

## PROGRAM
```python
import tkinter as tk


for b in self.buttons:
b.config(state=tk.DISABLED)


def reset(self):
self.board = [""] * 9
self.game_over = False
self.status_label.config(text="Your turn (X)")
for b in self.buttons:
b.config(text="", state=tk.NORMAL)




# Game logic
WIN_COMBINATIONS = [
(0, 1, 2), (3, 4, 5), (6, 7, 8),
(0, 3, 6), (1, 4, 7), (2, 5, 8),
(0, 4, 8), (2, 4, 6)
]


def check_winner(board):
for a, b, c in WIN_COMBINATIONS:
if board[a] and board[a] == board[b] == board[c]:
return board[a]
return None


def is_board_full(board):
return all(cell != "" for cell in board)




def minimax(board, depth, is_maximizing, alpha, beta):
winner = check_winner(board)
if winner == AI:
return 10 - depth
elif winner == HUMAN:
return depth - 10
elif is_board_full(board):
return 0


if is_maximizing:
max_eval = -999
for i in range(9):
if board[i] == "":
board[i] = AI
eval = minimax(board, depth + 1, False, alpha, beta)
board[i] = ""
max_eval = max(max_eval, eval)
alpha = max(alpha, eval)
if beta <= alpha:
break
return max_eval
else:
min_eval = 999
for i in range(9):
if board[i] == "":
board[i] = HUMAN
eval = minimax(board, depth + 1, True, alpha, beta)
board[i] = ""
min_eval = min(min_eval, eval)
beta = min(beta, eval)
if beta <= alpha:
break
return min_eval




def best_move(board):
best_score = -999
move = None
for i in range(9):
if board[i] == "":
board[i] = AI
score = minimax(board, 0, False, -999, 999)
board[i] = ""
if score > best_score:
best_score = score
move = i
return move




if __name__ == "__main__":
root = tk.Tk()
app = TicTacToeGUI(root)
root.mainloop()
```
<hr>
<h2>Sample Input and Output:</h2>


<img width="408" height="533" alt="Screenshot 2025-10-24 085630" src="https://github.com/user-attachments/assets/007f6dbe-0b1a-4d76-9c89-711b4c03216d" />


## RESULT
We have successfully implemented Alpha-beta pruning of Minimax Search Algorithm for a Simple TIC-TAC-TOE game.
