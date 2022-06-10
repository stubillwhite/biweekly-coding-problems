# World Cup Prognostication #

This week we're doing a fun game from Programming Praxis:

[World Cup Prognostication](https://programmingpraxis.com/2010/06/29/world-cup-prognostication/)

The ELO rankings of the various teams is available on [Wikipedia](https://en.wikipedia.org/wiki/World_Football_Elo_Ratings),
and the brackets are available in a several places, including [Wikipedia](https://en.wikipedia.org/wiki/2018_FIFA_World_Cup#Schedule).

To save you a little time looking things up, you can calculate the probability of team A beating team B using the
following formula:

    P(A) = 1/(1+10^m) where m is the rating difference (rating(B)-rating(A)) divided by 400

For fun, let's try doing this for the Women's Euro 2022 tournament, which is running now:

- Brackets are on [Wikipedia](https://en.wikipedia.org/wiki/UEFA_Women%27s_Euro_2022)
- ELO ratings are on [Everybody Soccer](https://everybodysoccer.com/even-the-goalkeepers-like-to/2016/8/20/womens-international-football-elo-ratings)

To save you a little time, here's what they currently are:

```
    England                     1692
    Germany                     1775
    Netherlands                 1726
    Denmark                     1503
    Norway                      1537
    Sweden                      1801
    France                      1832
    Belgium                     1374
    Iceland                     1476
    Spain                       1668
    Finland                     1210
    Austria                     1380
    Italy                       1582
    Switzerland                 1327
    Northern Ireland             980
    Portugal                    1248
```
