# Mastermind

Last week's challenge was Dawkins' Weasel, in which we evolved a string to match a desired pattern. When discussing the
problem we started talking about the similarities to the old board game Mastermind. This week we're going to implement
that game.

If you're not familiar with Mastermind, it is a game for two players in which a CodeMaker constructs a hidden code that
the CodeBreaker must guess by a process of elimination.

- The CodeMaker creates a hidden code by picking four out of six different colored CodePegs. The CodePegs are coloured
  red, blue, yellow, green, white, and black, and the CodeMaker may pick two or more of the same colour if desired. The
  chosen code is hidden behind a screen so the CodeBreaker cannot see it.
- The CodeBreaker attempts to guess the hidden code by matching the position and colours of the pegs
  - The CodeBreaker places four pegs to reflect their current guess
  - The CodeMaker places KeyPegs (coloured black and white) to show how close the guess is to the actual code. Note that
    the order of the feedback pegs is not related to the order of the code pegs, because that would give the game away
    somewhat. KeyPegs are placed as follows: 
    - A white KeyPeg for each CodePeg of the guess which is the right colour but in the wrong place
    - A black KeyPeg for each CodePeg of the guess which is the right colour and in the right place
    - If there are duplicate colours in the guess then they are only awarded a KeyPeg if they correspond to the same
      number of duplicate colurs in the code. For example, if the code is red-red-blue-blue and the guess is
      red-red-red-blue then the feedback is black black black; two reds are in the correct position, one blue is in the
      correct position, and there is no indication that there is another blue in the code.
 - The game continues with alternating guesses and feedback until either the code is guessed, or the CodeBreaker runs out
   of guesses (of which they have ten)

There is a good example of the game on [WikiHow](https://www.wikihow.com/Play-Mastermind), but here is a simple example
of calculating feedback:

    | Code     | Red   | Blue  | Green | Black  | Feedback          |
    |----------+-------+-------+-------+--------+-------------------|
    | Guess #1 | Black | Blue  | White | Green  | Black White White |
    | Guess #2 | Black | White | Green | Yellow | Black White       |

The first guess has black (right colour, wrong place), blue (right colour, right place), white (wrong), and green (right
colour, wrong place), so the feedback is: black, white, white.

The second guess has black (right colour, wrong place), white (wrong), green (right color, right place), and yellow
(wrong), so the feedback is: black, white.


For this week's hack, create the game with the computer as CodeMaker and a human as CodeBreaker. 

If you want an extra challenge, you can create a computer CodeBreaker. There are two algorithms listed on the
[Wikipedia](https://en.wikipedia.org/wiki/Mastermind_\(board_game\)) page for the game. One is by Knuth, which will solve
the game in five moves or less by maximising the information learned at each stage. The other is a genetic algorithm,
which might fit well with last week's challenge on genetic programming.
