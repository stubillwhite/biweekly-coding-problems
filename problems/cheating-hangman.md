# Cheating Hangman #

This week we're doing a fun game from Programming Praxis: 

[Cheating Hangman](https://programmingpraxis.com/2011/12/27/cheating-hangman/)

The basic idea is that the computer will change the word it is thinking of if you manage to
correctly guess a letter, but it can only change to something that doesn't make any of its previous
answers untrue. For example:

- Let's imagine we have a small dictionary with the words "cat", "car", "cow", "dog", "pig"
- The computer picks the word "cat" and tells you the number of letters you have to guess, which in this case is three: "- - -"
- You guess "o", which matches no letters, so the computer sticks with "cat" and displays "- - -"
- You guess "i", which matches no letters, so the computer sticks with "cat" and displays "- - -"
- You guess "c", which matches the first letter of "cat". The computer tries to switch words but it can't because "cow", "dog", and "pig" contain letters that it said were not in the word. It could switch to "car" but doing so would not help, so it sticks with "cat". It concedes letter "c"  and displays "c - -".
- You guess "a", which matches the second letter of "cat". The computer tries to switch words but it can't because both "cat" and "car" match that letter, so it concedes "a" and displays "c a -"
- You guess "t", which matches the third letter of "cat". The computer can change its word to "car" to avoid conceding a letter so it does so, and tells you it didn't match and displays "c a -"
- You guess "r", which matches the third letter of "car". The computer has no other words it can switch to so it concedes the game.

Bonus points for drawing a cute ASCII dude.
