# TicTacToe-Forward_Chaining

The AI's move logic was improved by introducing heuristics. 
Instead of checking all available cells, the AI player first looked for opportunities to create 'n' consecutive moves (O's) in a row, column, or diagonal, as this would be an advantageous move.

The main logic of the AI player's move was implemented using forward chaining. The AI player now analyzes the board to identify potential winning moves, blocking moves, and moves that would create 'n' consecutive O's without being blocked by the player. It uses forward chaining to prioritize these moves based on their strategic importance.

Working of Forward chaining:
Forward chaining is also known as a forward deduction or forward reasoning method when using an inference engine. Forward chaining is a form of reasoning which starts with atomic sentences in the knowledge base and applies inference rules (Modus Ponens) in the forward direction to extract more data until a goal is reached.
“The Forward-chaining algorithm starts from known facts, triggers all rules whose premises are satisfied, and adds their conclusion to the known facts. This process repeats until the problem is solved”.

The control flow of the Tic Tac Toe (Forward Chaining) game can be outlined as follows:
1. The program starts with the `main()` function, which acts as the entry point to the game.
2. The user is prompted to enter the board size (n) through the console.
3. The `initialize_board(n)` function creates an empty n x n grid as the Tic Tac Toe board. 4. The initial state of the board is displayed using the `display_board(board)` function.
4. The game enters into a loop where the player and AI take turns until the game is won by either the player, the AI, or it's a draw.

Player's Turn:
1. The user is asked to input their move by providing row and column indices through the console.
2. The input is validated to ensure it represents an empty cell on the board.
3. If the move is valid, an 'X' is placed in the chosen cell on the board.
4. The board is then displayed again using the `display_board(board)` function.
5. The game checks if the player has won using `check_win('X', board)` and if the board is full using `is_board_full(board)`.

AI's Turn:
1. The AI player determines its move using the `ai_move(board, n)` function.
2. The AI uses a heuristic approach to identify the best move by analyzing the board strategically.
3. If no winning or blocking move is available, the AI looks for opportunities to create 'n' consecutive 'O's in a row, column, or diagonal.
4. If no such move is available, the AI selects a random empty cell to place an 'O'.
5. The board is displayed after the AI's move using the `display_board(board)` function. - The game checks if the AI has won using `check_win('O', board)` and if the board is
full using `is_board_full(board)`.
6. If either the player or the AI has won, the game announces the winner. If the board is full and there is no winner, the game declares a draw.
7. The game ends, and the program exits.

Explanation of each function:

  a) The `initializeBoard(n)` function takes an integer `n` as input and returns an `n x n` grid representing the Tic Tac Toe board, initialized with empty cells represented by spaces.
  
  b) The `displayBoard(board)` function prints the current state of the board in a user-friendly format, showing the positions of 'X' and 'O' with vertical and horizontal separators.
  
  c) The `checkWin(player, board)` function checks if a given player ('X' or 'O') has won the game on the current board. It checks for winning conditions in rows, columns, and  diagonals, and returns `True` if the player has won; otherwise, it returns `False`.
  
  d) The `isBoardFull(board)` function checks if the board is completely filled with 'X' and 'O', indicating a draw. It returns `True` if the board is full; otherwise, it returns `False`.
  
  e) The `checkOs(player, count, blockedCount, n)` function is a helper function used to check if there are 'n' consecutive occurrences of a player's move (either 'X' or 'O') in a row, column, or diagonal, without any blocking moves by the opponent. It returns `True` if the condition is met; otherwise, it returns `False`.
  
  f) The `checkNO(player, board, n)` function checks if the AI player can create 'n' consecutive 'O's on the board without being blocked by the player. It uses the helper function `checkOs` to analyze rows, columns, and diagonals and returns `True` if the condition is met; otherwise, it returns `False`.
  
  g) The `aiMove(board, n)` function is responsible for the AI player's move. It employs a heuristic approach:
  1. First, it checks if the AI can win the game in the next move. If so, it places an 'O' in the winning position.
  2. Next, it checks if the AI needs to block the player from winning. If so, it places an 'O' to block the player's winning move.
  3. If no winning or blocking move is available, the AI tries to create 'n' consecutive 'O's to establish a winning condition in the future.
  4. If none of the above conditions are met, the AI chooses a random empty cell to place an 'O'.
    
h) The `main()` function is the entry point to the game. It prompts the user to enter the board size (n) and initializes the board accordingly. The game loop alternates between the player's and AI's moves until a player wins or the game ends in a draw. The player's move is taken as input, and the AI's move is determined by the `aiMove()` function.

i) After each move, the game checks for a winner or a draw and displays the current state of the board using `displayBoard()`. The game continues until a result is reached.
  1. The program ends when the game is won by either the player or the AI, or when the game ends in a draw.
  2. The result is a functional Tic Tac Toe game with an AI opponent that strategically analyzes the board to make intelligent moves, providing an engaging gaming experience for the         players.
