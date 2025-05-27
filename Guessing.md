```mermaid
flowchart TD
    Start([Start]) --> GenerateRandom{Generate random number};
    GenerateRandom --> GetUserGuess[Get user's guess];
    GetUserGuess --> IsValidInput{Is input valid? (numeric, in range)};
    IsValidInput -- No --> InformInvalid[Inform user of invalid input] --> GetUserGuess;
    IsValidInput -- Yes --> CompareGuess{Is guess == secret number?};
    CompareGuess -- Yes --> Win([You Win!]);
    CompareGuess -- No --> CheckHighLow{Is guess > secret number?};
    CheckHighLow -- Yes --> TooHigh[Too high!] --> GetUserGuess;
    CheckHighLow -- No --> TooLow[Too low!] --> GetUserGuess;

    ## Flowchart Description

This flowchart outlines the logic of a number guessing game where the computer selects a random secret number, and the player tries to guess it.

1.  **Start:** The game begins execution.

2.  **Generate random number:** The computer generates a random integer within a predefined range (e.g., between 1 and 100). This number remains the secret for the current game.

3.  **Get user's guess:** The game prompts the player to enter their guess for the secret number.

4.  **Is input valid? (numeric, in range):** The game checks if the player's input is a valid number and, if the game specifies a range, whether it falls within that range.
    * **No:** If the input is not a valid number or is outside the specified range, the flow moves to "Inform user of invalid input."
    * **Yes:** If the input is valid, the flow proceeds to "Compare guess."

5.  **Inform user of invalid input:** The game displays a message to the player indicating that their input was not valid and prompts them to enter a guess again ("Get user's guess").

6.  **Is guess == secret number?:** The game compares the player's valid guess to the computer's secret number.
    * **Yes:** If the guess matches the secret number, the flow moves to "You Win!"
    * **No:** If the guess is incorrect, the flow proceeds to "Check high/low."

7.  **You Win!:** The game displays a congratulatory message to the player, indicating they have guessed the correct number, and the game ends.

8.  **Is guess > secret number?:** If the guess was incorrect, the game determines if the player's guess was higher than the secret number.
    * **Yes:** If the guess is higher, the flow moves to "Too high!"
    * **No:** If the guess is not higher (meaning it must be lower), the flow moves to "Too low!"

9.  **Too high!:** The game provides feedback to the player that their guess was too high and prompts them to enter another guess ("Get user's guess").

10. **Too low!:** The game provides feedback to the player that their guess was too low and prompts them to enter another guess ("Get user's guess").

This flowchart comprehensively covers the core logic of the guessing game, including random number generation, user input, basic input validation, comparison, feedback, and the win condition with a loop for subsequent guesses.
