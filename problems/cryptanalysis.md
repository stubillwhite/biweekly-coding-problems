# Cryptanalysis #

This time we're going to have a little play with some really simple cyphers and cryptanalysis. For each, we'll implement
the cypher and the implement something to break it.

## Caesar cypher ##

Everyone knows this cypher -- encrypt each letter by shifting it by the value of the key, and decrypt by deducting the
value of the key. There's a good description here: https://en.wikipedia.org/wiki/Caesar_cipher

1) First of all, let's implement the cypher. Note that before encrypting, the input text (usually called the plaintext)
   will need to be normalised -- you should uppercase all the letters and strip out any punctuation apart from spaces.

2) Once you've implemented the cypher, let's break it. An easy way to do this is with frequency analysis, which is
   described here: https://en.wikipedia.org/wiki/Frequency_analysis
   
   We can write something that will calculate the frequencies of the letters in a piece of sample text. By comparing
   this to the frequencies of the letters in the encrypted text (usually called the cyphertext), we can work out what
   the most probable key is.
   
If the sample text is similar to the original plaintext then the frequencies will be close enough that this will work.
Obviously, if they're very different (e.g., you encrypt something in French and try to guess the key using English
sample text then it's not going to work...)

## Vigenere cypher ##

Vigenere is a series of Caesar cyphers in sequence, with the shift values specified by the key. There is a good
description of the cypher here: https://en.wikipedia.org/wiki/Vigen%C3%A8re_cipher#Description.

1) Implement Vigenere to encrypt or decrypt given a particular key.

2) Once it's implemented, let's break it. There's a good description of how this was broken here:
   https://en.wikipedia.org/wiki/Kasiski_examination
   
   There are two steps to breaking it: find out probable key periods by looking for repeated fragments in the cypher
   text, then for each probable key length try to work out the key using the same frequency analysis as for the Caesar
   cypher.
