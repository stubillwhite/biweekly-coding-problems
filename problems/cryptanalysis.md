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

2) Once it's implemented, let's break it. There are two steps to breaking it: find the key length, then given the key
   length try to work out the key using the same frequency analysis as for the Caesar cypher.
   
### Finding the key length ###

This is a little unintuitive, so here's an explanation of an approach that works. To find the key length:

- For each probable key length N in 1 to 10 (say)
   - Sample the cyphertext every N characters to build N samples of the cyphertext
   - Calculate the Index of Coincidence for the N samples and take the mean, so you have a single number for each N
     which is the mean IOC for that N
        
There's an article on calculating the Index of Coincidence on Wikipedia here:
https://en.wikipedia.org/wiki/Index_of_coincidence

The formula is the sum of:

    (letterFreq * (letterFreq - 1)) / (totalLetters * (totalLetters - 1)) * totalNumberOfLettersInLanguage
    
Where:

- `letterFreq` = the frequency of each letter in the cyphertext
- `totalLetters` = the total length of the cyphertext
- `totalNumberOfLettersInLanguage` = the total number of letters in the language
        
What you’ll see is that the IoC jumps for the correct key length, and for multiples of it. So, if the key length is 3
then you’ll see a jump in IoC for 3, 6, 9, 12, etc.

Worked example:

Say we have the following cyphertext, encrypted with a key of length five:

    QPWKALVRXCQZIKGRBPFAEOMFLJMSDZVDHXCXJYEBIMTRQWNMEAIZRVKCVKVLXNEICFZPZCZZHKMLVZVZIZRRQWDKECHOSNYXXLSPMYKVQXJTDCIOMEEXDQVSRXLRLKZHOV
    
If we calculate the IoC for each of the key lengths up to twelve then we get the second column, and if for each row we
calculate the delta between the IoC and previous highest IoC then we get the third column.

    Length  IoC     Delta
    1       1.12    +0.00
    2       1.19    +0.07
    3       1.05    -0.14
    4       1.17    -0.02
    5       1.82    +0.65
    6       0.99    -0.83
    7       1.01    -0.82
    8       1.05    -0.78
    9       1.17    -0.65
    10      2.07    +0.24
    11      1.20    -0.63
    12      0.89    -0.93
    
Sorting by the delta, we can see that the most likely key length is 5, followed by 10, then the remainder are much less
likely.

    Length  IoC     Delta 
    5       1.82    +0.65 
    10      2.07    +0.24 
    2       1.19    +0.07 
    4       1.17    -0.02 
    1       1.12    +0.00 
    3       1.05    -0.14 
    11      1.20    -0.63 
    9       1.17    -0.65 
    8       1.05    -0.78 
    7       1.01    -0.82 
    6       0.99    -0.83 
    12      0.89    -0.93 

Once you know the key length then you can break Vigenere in the same way as you break Caesar.
