# Game of Blobs #

This time we're doing a fun challenge from Daily Programmer:

[Game of Blobs](https://www.reddit.com/r/dailyprogrammer/comments/aldexk/20190130_challenge_374_intermediate_the_game_of/)

There are a few clarifications to bear in mind:

- All blobs choose their destination at the same moment, move, and merge at the same moment
- It's possible that you'll end up with more than one blob in the end
- Larger blobs can merge with each other, for example if they collide when moving towards a common goal
- Often one will end up trailing another for some time
- The clockwise rule means that if you have three nodes at equal distance and all equal size then choose the node
  clockwise from 12 o'clock. For example, if you have three nodes of equal size and distance at 1 o'clock, at 5 o'clock,
  and at 11 o'clock, then you'll choose the one at 1 o'clock.
- As blobs try to minimise the distance there will be a preference for diagonal moves
