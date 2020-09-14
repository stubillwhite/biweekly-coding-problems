# Labyrinths Are Awesome - part one #

This week we're going to build a labyrinth. There are a variety of different algorithms for doing this, each of which
creates a labyrinth with slightly different characteristics. We're going to use the recursive backtracking algorithm,
which is as follows:

- Choose a random starting point in the grid
- Randomly choose an adjacent cell which has not been visited
  - Carve a passageway to that adjacent cell. This now becomes the current cell.
- If all adjacent cells have been visited
  - Backtrack along your path to the first cell which has an adjacent cell. This now becomes the current cell.
- Repeat until you backtrack to you the start point

Here's an example grid:
 
          A   B   C   D
        +---+---+---+---+
      1 |   |   |   |   |
        +---+---+---+---+
      2 |   |   |   |   |
        +---+---+---+---+
      3 |   |   |   |   |
        +---+---+---+---+
      4 |   |   |   |   |
        +---+---+---+---+
        
We randomly start at B1, and carve successively through the following cells: B1 B2 B3 B4 A4 A3 A2 A1

          A   B   C   D
        +---+---+---+---+
      1 |   |   |   |   |
        +   +   +---+---+
      2 |   |   |   |   |
        +   +   +---+---+
      3 |   |   |   |   |
        +   +   +---+---+
      4 |       |   |   |
        +---+---+---+---+
        
      Path: B1 B2 B3 B4 A4 A3 A2 A1

There are no cells adjacent to A1 which have not been visited, so we backtrack up our path: A1 A2 A3 A4 B4. B4 has cells
which have not been visited, so we start digging again and carve successively through the following cells: B4 C4 C3 D3 D4.

          A   B   C   D
        +---+---+---+---+
      1 |   |   |   |   |
        +   +   +---+---+
      2 |   |   |   |   |
        +   +   +---+---+
      3 |   |   |       |
        +   +   +   +   +
      4 |           |   |
        +---+---+---+---+

      Path: B1 B2 B3 B4 C4 C3 D3 D4
        
There are no cells adjacent to D4 which have not been visited, so we backtrack up our path again: D4 D3. D3 has cells
which have not been visited, so we start digging again and carve successively through the following cells: D3 D2 C2 C1 D1.
    
          A   B   C   D
        +---+---+---+---+
      1 |   |   |       |
        +   +   +   +---+
      2 |   |   |       |
        +   +   +---+   +
      3 |   |   |       |
        +   +   +   +   +
      4 |           |   |
        +---+---+---+---+
    
      Path: B1 B2 B3 B4 C4 C3 D3 D2 C2 C1 D1 

There are no cells adjacent to D4 so we backtrack up our path again: D1 C1 C2 D2 D3 C3 C4 B4 B3 B2 B1. We're now back at
the start, so the algorithm terminates.

Write something to generate and display a labyrinth of configurable size. 

If you want to get fancy, there are a number of other algorithms on Wikipedia
[here](https://en.wikipedia.org/wiki/Maze_generation_algorithm) which would be interesting to implement and produce
labyrinths with slightly different characteristics.

