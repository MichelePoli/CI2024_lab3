# 15-Puzzle Solver using A* Search Algorithm

This repository contains a Python implementation of the n²-1 puzzle solver using the **A\* search algorithm**. The goal of the puzzle is to rearrange a scrambled 4x4 grid to match a goal configuration using the least number of moves, where each move consists of sliding a tile into the blank space.

## Features

- **A\* Search Algorithm**: The solver uses A\* search with the Manhattan distance heuristic to find the shortest path to the goal configuration.
- **Manhattan Distance Heuristic**: A heuristic used to estimate the distance of a tile from its goal position, helping guide the search algorithm.
- **Random Puzzle Generation**: The initial puzzle configuration is randomly generated by shuffling the tiles.

## How It Works

1. **Puzzle Setup**: The puzzle is a 4x4 grid with 15 numbered tiles and one blank space (`0`). The goal is to arrange the tiles in numerical order, with the blank space at the bottom-right corner.
   
2. **State Representation**: Each state of the puzzle is represented as a 2D NumPy array, with `0` as the blank space.

3. **A\* Search**:
   - The algorithm explores possible moves and prioritizes the states based on the cost function `f(n) = g(n) + h(n)`, where:
     - `g(n)` is the number of moves taken to reach the current state.
     - `h(n)` is the Manhattan distance from the current state to the goal state.
   - The search continues until the goal state is reached.

4. **Solution Path**: Once the goal state is found, the sequence of moves (states) is reconstructed by backtracking through the parent states.

## Functions

- **`find_blank(state)`**: Returns the coordinates of the blank space (`0`).
- **`is_goal(state)`**: Checks if the current state is the goal state.
- **`get_possible_moves(state)`**: Returns a list of valid moves (up, down, left, right) for the blank space.
- **`move_blank(state, new_blank_pos)`**: Returns a new state after moving the blank space.
- **`manhattan_distance(state)`**: Calculates the Manhattan distance heuristic for the current state.
- **`a_star_search(initial_state)`**: Solves the puzzle using the A\* search algorithm and returns the solution path.


