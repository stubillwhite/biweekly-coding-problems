# Cryptanalysis #

This week we're going to handle some basic cryptanalysis.

## Part one - Monoalphabetic substitution cipher ##

Implement a simple random substitution cipher. There's a good description here:
https://en.wikipedia.org/wiki/Substitution_cipher

Now that we've done that, let's try to break it.
https://en.wikipedia.org/wiki/Frequency_analysis

## Part two - Polyalphabestic substitution cipher ##

Vigenere is a series of Caesar ciphers in sequence, with the shift values specified by the key. There is a good
description of the cipher here: https://en.wikipedia.org/wiki/Vigen%C3%A8re_cipher#Description. Implement Vigenere to
encode or decode given a particular key.

Now let's break it. Kasiski was the first to break Vigenere by looking for repeated patterns of encoded letters which
provide a clue to the period of the key. Once the period of the key is known, each of the sequence of Caesar ciphers can
be broken using frequency analysis or interactive guesswork, as with the monoalphabetic substitution cipher we broke
previously. There's a good description here: https://en.wikipedia.org/wiki/Kasiski_examination

Implement Kasiski's method.
