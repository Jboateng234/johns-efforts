# Tic Tac Toe Game in Python

# Function to print the Tic Tac Toe board
def print_board(board):
    for row in board:
        print(" | ".join(row))
        print("-" * 9) # For separating rows

# Function to check if a space on the board is free
def is_space_free(board, row, col):
    return board[row][col] == " "

# Function to check if the board is full
def is_board_full(board):
    for row in board:
        for cell in row:
            if cell == " ":
                return False
    return True

# Function to check for a win
def check_win(board, mark):
    # Check rows, columns, and diagonals for a win
    for i in range(3):
        if board[i][0] == board[i][1] == board[i][2] == mark: # Check rows
            return True
        if board[0][i] == board[1][i] == board[2][i] == mark: # Check columns
            return True

    # Check diagonals
    if board[0][0] == board[1][1] == board[2][2] == mark or board[0][2] == board[1][1] == board[2][0] == mark:
        return True

    return False

# Main function to run the game
def play_game():
    # Initializing the board
    board = [[" " for _ in range(3)] for _ in range(3)]
    current_player = "X"

    while True:
        print_board(board)
        print(f"Player {current_player}'s turn.")

        # Getting player's move
        row = int(input("Enter row (0, 1, 2): "))
        col = int(input("Enter column (0, 1, 2): "))

        # Check if the move is valid
        if 0 <= row <= 2 and 0 <= col <= 2 and is_space_free(board, row, col):
            board[row][col] = current_player
        else:
            print("Invalid move, try again.")
            continue

        # Check for a win or tie
        if check_win(board, current_player):
            print_board(board)
            print(f"Player {current_player} wins!")
            break
        elif is_board_full(board):
            print_board(board)
            print("The game is a tie!")
            break

        # Switch player
        current_player = "O" if current_player == "X" else "X"

# Start the game
play_game()
