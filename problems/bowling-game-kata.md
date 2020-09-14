# Bowling Game Kata #

This week we're doing a fun exercise from Programming Praxis:

[Uncle Bob's Bowling Game Kata](https://programmingpraxis.com/2009/08/11/uncle-bobs-bowling-game-kata/)

In case the description isn't clear, here's how scoring in bowling works:

    1 4 | 4 5 | 6 / | 5 / |   X | 0 1 | 7 / | 6 / |   X | 2 / 6
      5 |  14 |  29 |  49 |  60 |  61 |  77 |  97 | 117 |   133

- The game consists of 10 frames, as shown in the table above.

- In each frame the player has two opportunities to knock down 10 pins. In the table, the score for each ball is shown
  on the first row. The score for the frame is the total number of pins knocked down, plus bonuses for strikes and
  spares. 
  
  - So, in the first frame above, the player knocked down a single pin with the first ball, then 4 of the remaining 9
    pins with the second ball, giving a total score for the frame of 5, bringing the running score up to 5 (shown on the
    second row).

- A spare is when the player knocks down all 10 pins in two tries. The bonus for that frame is the number of pins
  knocked down by the next roll. 
  
  - So in frame 3 above, the score is 10 (the total number knocked down) plus a bonus of 5 (the number of pins knocked
    down on the next roll), which brings the running score up to 29 (previous score of 14 plus 15 for this frame)

- A strike is when the player knocks down all 10 pins on his first try. The bonus for that frame is the value of the
  next two balls rolled.

- In the tenth frame a player who rolls a spare or strike is allowed to roll the extra balls to complete the frame.
  However no more than three balls can be rolled in tenth frame.
