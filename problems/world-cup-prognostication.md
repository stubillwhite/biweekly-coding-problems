# World Cup Prognostication

This week we're doing a fun game from Programming Praxis:

[World Cup Prognostication](https://programmingpraxis.com/2010/06/29/world-cup-prognostication/)

The ELO rankings of the various teams is available on [Wikipedia](https://en.wikipedia.org/wiki/World_Football_Elo_Ratings),
and the brackets are available in a several places, including [Wikipedia](https://en.wikipedia.org/wiki/2018_FIFA_World_Cup#Schedule).

To save you a little time looking things up, you can calculate the probability of team A beating team B using the
following formula:

    P(A) = 1/(1+10^m) where m is the rating difference (rating(B)-rating(A)) divided by 400
