# Minesweeper Part One #

Over the next couple of weeks we're going to be doing a fun exercise from Hacker Rank:

[Minesweeper](https://www.hackerrank.com/contests/practice-test-6/challenges/minesweeper-1)

For this first week, just concentrate on getting the game up and running. If you're not familiar with the game then
there's a good description on [Wikipedia](https://en.wikipedia.org/wiki/Minesweeper_(video_game)). There are also a few
sites where you can play the game online, such as [Minesweeper Online](http://minesweeperonline.com/).

The game consists of a grid of squares whose contents is hidden. The player selects squares one by one, which reveals
their contents. A square can contain:

- Nothing
- A mine, in which case the game is lost
- A number between 1 and 8 inclusive which indicates the number of mines adjacent to this square (vertically,
  horizontally, and diagonally)

If an empty square is revealed on then the surrounding squares should also be revealed; any of these are also empty then
those squares are also revealed, and so on, which may result in a large area being revealed in a single action. The game
is won when the only hidden squares are those covering mines.

Next week we'll be looking at a solver for the game.
