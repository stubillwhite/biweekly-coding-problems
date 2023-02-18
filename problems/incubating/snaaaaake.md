## Snaaaaake ##

This time we're going to implement the game Snake. There's a Wikipedia page that describes it here:

[Snake](https://en.wikipedia.org/wiki/Snake_(video_game_genre))

The basic game is as follows:

- The user controls a snake that can move in four directions (up, down, left, right) using the arrow keys
- The user controls the snake's head, and the snake's body follows the head
- The game updates every second and the snake will move one square in the direction that it was last heading
- The snake an only turn anticlockwise or clockwise, and it cannot turn back on itself. So, if the snake is heading to
  the right, the user can press up to head up or down to head down, but pressing either right or left will do nothing
  (the former is the direction the snake is heading in anyway, and the latter would attempt to turn back on itself)
- The game is over if the snake collides either with it's own body, or with the border around the play area
- The play area contains a randomly located blob of food, and if the snake's head touches this then it is eaten and the
  snake body grows by one square in length, and a new blob of food is randomly placed in the play area

Let's implement the basic game as above.

If you have time and want to tinker with this a bit more then there are a few additional challenges you could play with:

- Add a score -- There is a score counter, and each piece of food is worth one point
- Different foods -- Instead of just adding one square to the snake, different foods can increase the length by
  different amounts
- Add walls -- Put a few walls in the play area to make movement more challenging
- Computer controlled snake -- Make the computer control the snake's movement. For this, you'll want to implement some
  basic path-finding, and the A* algorithm
  ([[https://medium.com/@nicholas.w.swift/easy-a-star-pathfinding-7e6689c7f7b2][Easy A* Pathfinding]]) will work well
- Mobile food -- We can make the food attempt to run away from the snake so it has to chase it. Food should move more
  slowly than the snake (so it move once every two turns, rather than every turn). To make it run away, we can reuse A*
  and instead of picking the best square to move towards the snake's head, the food can pick the worst square,
  effectively moving directly away from it

