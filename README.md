# Rock Paper Scissors Game Logic

### Import libraries
- Import `random` library for the computer choices in the game
- Import `tkinter` library for GUI purposes (Graphic User Interface)
- Import `messagebox` from `tkinter` to display result message after game finishes
- Import `Python Image Language` for `Image` and `ImageTk` that handles images

## Creating the game logic

### Game Class
-The `Game` class encapsulates the logic of the Rock Paper Scissors game. 
-It provides methods for getting the computer's choice, getting the user's choice, determining the winner, and playing the game.

#### `get_computer_choice()`
- **Static Method**: This method is marked with `@staticmethod` because it doesn't rely on any instance-specific data. 
- It simply returns a random choice of "Rock", "Paper", or "Scissors" for the computer.

#### `get_user_choice()`
- **Static Method**: Similar to `get_computer_choice()`, this method is marked with `@staticmethod` because it doesn't require any instance-specific data.
- It prompts the user for input and returns their choice after validating it against the list of valid choices.

#### `get_winner(user_choice, computer_choice)`
- **Static Method**: Again, marked with `@staticmethod` because it operates on the input choices without needing access to instance-specific data.
- It compares the user's and computer's choices to determine the winner based on the rules of Rock Paper Scissors.

#### `play()`
- **Class Method**: This method is marked with `@classmethod` because it operates on the class itself rather than an instance of the class. 
- It simulates playing the game, alternating between getting the user's choice and generating the computer's choice until one side wins three rounds or five rounds have been played.

## Creating the game GUI 

### `play_game()`
- This function creates and runs the Tkinter GUI for the Rock Paper Scissors game
- Uses the image library to import a background onto the game

#### `play_round()`
- Nested function to handle the gameplay when a button is clicked
- Also updates the game's statistics and results display
- If either the user or computer wins three rounds, display a message box indicating the game's result and reset the game

#### `reset_game()`
- Reset game statistics and clear labels.

#### Initialise variables for tracking game statistics
- `computer_choice_label`: Label to display the computer's choice.
- `rounds_played_label`: Label to display the current round number.
- `result_label`: Label to display the result of each round.
- `score_label`: Label to display the current score of the game.

#### Create buttons 
- Create buttons for the game choices ("Rock", "Paper", "Scissors") using a loop and place them on the GUI.

#### Create labels
- Create labels to display computer choice, round number, result, and score, and place them on the GUI.

#### Start Tkinter
- Start the game using `play_game()`

### Explanation of Logic

- Each button representing a game choice ("Rock", "Paper", "Scissors") has a command attached to it, which calls the `play_round` function with the corresponding choice.
- Inside `play_round`, the computer's choice is determined using the `get_computer_choice` method from the `Game` class, and the winner is determined using the `get_winner` method.
- Game statistics such as the number of rounds played, user wins, and computer wins are updated accordingly.
- If either player wins three rounds, a message box is displayed indicating the game's result, and the game is reset.
