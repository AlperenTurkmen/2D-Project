# Word Puzzle Game

A Unity-based word puzzle game inspired by popular word guessing games. The player attempts to guess a target word by entering letters. The game provides feedback on each guess, indicating correct, incorrect, or misplaced letters.

## Table of Contents
- [Overview](#overview)
- [Features](#features)
- [Getting Started](#getting-started)
- [Project Structure](#project-structure)
- [Scripts Explanation](#scripts-explanation)

## Overview
In this game, players guess a hidden word by entering letters. Each guess is validated against a list of possible words, and feedback is provided for each letter:

- **Green** for correct letters in the correct positions.
- **Yellow** for correct letters in the wrong positions.
- **Gray** for incorrect letters.

The game provides options to start a new game or retry the same word.

## Features
- Input handling for alphabetic characters.
- Word validation against a predefined list of solutions and valid words.
- Feedback for each guess with visual indicators for letter states.
- Easy-to-use UI for starting a new game or trying again.

## Getting Started
### Prerequisites
- **Unity**: Version 2021.3 or later is recommended.
- **TextMeshPro**: Ensure that TextMeshPro is installed through the Unity Package Manager, as the game uses it for displaying text.

### Setup
1. **Clone the Repository**:

   ```bash
   git clone https://gitlab.com/yourusername/word-puzzle-game.git
   ```

2. **Open the Project**:
   - Open Unity Hub and add the cloned project folder.
   - Open the project in Unity.

3. **Set Up Word Lists**:
   - Place text files for valid words and solutions in the Resources folder.
   - Ensure they are named `official_wordle_common.txt` and `official_wordle_all.txt` for solutions and valid words, respectively.

4. **Run the Game**:
   - Open the `MainScene` in the Unity Editor.
   - Press the Play button in Unity to start the game.

## Project Structure
```
Assets/
|-- Scripts/
|   |-- Board.cs            # Manages game flow, input handling, and game logic
|   |-- Row.cs              # Represents a row of letter tiles
|   |-- Tile.cs             # Represents a single tile on the board
|-- Resources/
|   |-- official_wordle_common.txt  # List of target words
|   |-- official_wordle_all.txt     # List of valid guessable words
|-- Prefabs/
|   |-- Row.prefab          # Prefab for rows of tiles
|   |-- Tile.prefab         # Prefab for individual tiles
|-- Scenes/
|   |-- MainScene.unity     # Main scene for the game
```

## Scripts Explanation
### Board.cs
Handles the core game logic, including input handling, word validation, and updating the board.

**Key Methods**:
- `StartNewGame()`: Resets the game board and selects a new target word.
- `Update()`: Processes player input and updates the current row.
- `SubmitRow()`: Validates a player's guess and provides feedback.
- `HandleBackspace()` and `HandleLetterInput()`: Manage input for deleting and adding letters.

### Row.cs
Represents a row of tiles.

- Stores the guessed word formed by the player's inputs.
- `Awake()`: Initializes the tiles in the row.

### Tile.cs
Represents a single tile in the game.

- Displays a letter and changes its visual state based on feedback.

**Methods**:
- `SetLetter()`: Sets the displayed letter.
- `SetState()`: Updates the tile's color based on whether the letter is correct, incorrect, or misplaced.
