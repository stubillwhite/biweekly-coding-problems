# Game of Blobs #

This time we're doing a fun challenge from Daily Programmer:

[Game of Blobs](https://www.reddit.com/r/dailyprogrammer/comments/aldexk/20190130_challenge_374_intermediate_the_game_of/)

There are a few clarifications to bear in mind:

- All blobs choose their destination at the same moment, move, and merge at the same moment
- It's possible that you'll end up with more than one blob in the end
- Larger blobs can merge with each other, for example if they collide when moving towards a common goal
- Often one will end up trailing another for some time
- As blobs try to minimise the distance there will be a preference for diagonal moves

The discussion in Reddit suggests breaking ties by selecting the first prey clockwise from 12 o'clock. Feel free to do
so if you want to, but that adds a bit of complexity so we're bothering with that requirement.

If you complete the challenge and want to have a little fun, try adding the following rule:

- Instead of remaining static, if a blob has no prey smaller than it then it should move in a random direction (within
  the bounds of the world)

