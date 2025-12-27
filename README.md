An OCaml implementation of the popular Game Pigeon Word Hunt game, featuring an interactive GUI, intelligent board solving, and multiple game modes.

## Authors

- Nelson Zhang 
- James Tu 
- Benjamin Ratin 

## Overview

Word Hunt is a word puzzle game where players form words by connecting adjacent letter tiles on a 4x4 grid. The game challenges players to find as many valid words as possible within a time limit, with scoring based on word length and complexity.

## Features

- **Interactive GUI**: Built with Bogue library for a smooth gaming experience
- **Command-Line Mode**: Alternative text-based interface for playing
- **Intelligent Board Solver**: Automatically finds all possible valid words on any board
- **Trie Data Structure**: Efficient word lookup and validation using the Scrabble dictionary
- **Two Game Modes**: Normal and Survival modes with different challenges
- **Real-time Scoring**: Dynamic scoring system based on word length
- **Comprehensive Testing**: Full test suite with code coverage reporting

## Game Modes

### Normal Mode
- **Duration**: 60 seconds
- **Objective**: Score as many points as possible before time runs out
- **Scoring**:
  - 3 letters: 100 points
  - 4 letters: 400 points
  - 5 letters: 800 points
  - 6 letters: 1,400 points
  - 7 letters: 2,000 points
  - 8+ letters: 3,000 points
- **End Screen**: Displays final score and the longest possible words from the board

### Survival Mode
- **Starting Time**: 20 seconds
- **Objective**: Keep playing by finding words to add time to the clock
- **Time Bonuses**:
  - 3 letters: +5 seconds
  - 4 letters: +7 seconds
  - 5 letters: +12 seconds
  - 6 letters: +20 seconds
  - 7 letters: +30 seconds
  - 8+ letters: +45 seconds
- **Scoring**: Same as Normal Mode
- **Challenge**: Game ends when timer reaches zero

## Gameplay Rules

1. **Word Formation**: Connect adjacent tiles (including diagonally) to form words
2. **Minimum Length**: Words must be at least 3 letters long
3. **No Tile Reuse**: Each tile can only be used once per word
4. **Valid Words**: Only words from the Scrabble dictionary are accepted
5. **Unique Entries**: Duplicate words won't earn additional points

### Example
Given the board:
```
C A T D
W O F O
I R D G
N O A S
```
Valid words include: CAT, DOGS, WORDS, TORN
- "AT" would be rejected (too short)
- "TFGD" would be rejected (not a real word)

## Installation

### Prerequisites
1. Install OCaml and opam (if not already installed)
2. Install Bogue dependencies:
   ```bash
   opam install dune tsdl tsdl-image tsdl-ttf
   ```
3. Install Bogue:
   ```bash
   opam install bogue
   ```

### Build
```bash
make build
```

## Usage

### GUI Mode (Recommended)
```bash
make GUI
```
Then full-screen the pop-up window and select your preferred game mode.

### Command-Line Mode
```bash
make game
```
Enter words using coordinate notation, e.g., `(0,0);(0,1);(0,2)` for the top-left three letters.

### Run Tests
```bash
make test
```

### Generate Code Coverage
```bash
make bisect
```

### Generate Documentation
```bash
make doc
make opendoc
```

## Project Structure

```
Word-Hunt/
├── src/
│   ├── builder.ml/mli       # Board generation and word validation
│   ├── data_structures.ml/mli # Trie and Dictionary modules
│   └── dune                  # Source build configuration
├── bin/
│   ├── GUI.ml               # Bogue-based graphical interface
│   ├── game.ml              # Command-line interface
│   └── dune                 # Binary build configuration
├── tests/
│   └── tests.ml             # Comprehensive test suite
├── data/
│   ├── scrabble_dict.txt   # Scrabble dictionary for word validation
│   └── instructions.txt     # Game instructions
├── Makefile                 # Build and run commands
└── README.md               # This file
```


This project was created as a final project for Cornell CS 3110.