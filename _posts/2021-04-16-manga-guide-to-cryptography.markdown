---
layout: post
title:  "TL;DR - A Manga Guide to Cryptography"
date:   3021-04-05 15:00:00 -0400
categories: career
featured_image: '/images/featured/placeholder.jpg'
excerpt:

---


Sitani and Sato argue that “there is no doubt that protecting information is the most important issue that faces us in the age of networking”, and that the need for proficiency in cryptography is no longer strictly the domain of specialists but a necessity for everyone, including users.

The tanuki cipher is based on a Japanese wordplay game. People send “coded” messages to each other by adding superfluous instances of the syllable “TA”, leaving the message otherwise intact. Depending on how one reads the kanji for “Tanuki”, it can either read “Raccoon” or “Omit The TA’s”. This is actually a common trope in English; if I say ixnay you probably know what I mean. Sweden similarly has “Fikonspraket”. Needless to say this is not sufficient cryptography.

Okay but did you have to make Ms. Cipher really sultry though?
I like this dynamic where his sister is way smarter than he is.

—————


Codes and ciphers aren’t the same thing.
A cypher is a series of operations you use to obfuscate a piece of data.

Claude Shannon, known as the father of information theory, wrote a paper in the late 40’s called “A Mathematical Theory of Communication. This is where the term “bit” comes from. He also has this neat encryption model which you can use to talk about data during the encryption process.
(lowercase) m = a plaintext message, unaltered.
(uppercase) C = is the final encrypted message, or ciphertext.
(subscript) Ek = the process of encryption, transforming one into the other.
(Subscript) Dk = the opposite
(lowercase) k = encryption key, the algorithm used to obscure m. Any series of operations can be k.
(lowercase) n = an unknown number. Just like in mathematics.
Random Greek characters = abbreviation for different conversion / substitution rules in a problem.
A substitution rule is not necessarily the entirety of k, but may be a step.


Other common terminology are the generic “Bob” and “Alice” for generic senders and recipients, and the nefarious “Eve” in the middle.
Bet you a dollar this is biblical or some patriarchal shit.
Sure enough, some scholars in the science community straight up write fan-fiction about these non-characters and their failed marriage. It’s both charming and disturbing how nerds can project like this.


Classic encryption methods (these are too simple and well known to be used today)
Substitution ciphers - The replacement of one letter of m with another plaintext letter, in which all instances of a letter in m have the same corresponding value.
Caesar Cipher - A rotation cypher and subtype of substitution cyphers, which creates ciphertext by shifting each letter of plaintext n number of letters through the alphabet, where z wraps around to a. Used by Julius Caesar to confound his rivals long enough to take over New Vegas. Wait…
Polyalphabetic Cipher - m is divided into fixed-size blocks of n letters, and each character shifts a varying number of letters in the alphabet.
Example of a conversion rule for an eight letter word:
Blocks are 4 characters each
First letter shifts 2
Second letter shifts 5
Third letter shifts 3
Fourth letter shifts 1
Transposition Cipher - After breaking the plaintext into fixed sized blocks, the sequence of the numbers inside those blocks are switched around. You’re probably familiar with this if you do like, newspaper word scrambles.

Key Space = the total number of possible keys in a cipher. That means the key space is the maximum number of attempts someone could need to break the code.
A Caesar cypher using a modern English alphabet would be P=26, since the order of letters does not change.
If you shuffled all the letters randomly but kept a 1:1 mapping (like a function), instead you’d have: (26)P(26) (sorry I can’t do subscript). That can also be written 26! Or 26 factorial.
That would be equal to 4.03291461 x 10 ^ 26.
The subscript represents the number of total characters to choose from, followed by the number of them you’re using in the cypher.

(uppercase) P = permutations, or unique arrangement of characters in a sequence.
If order doesn’t matter, it’s called a combination instead, and abbreviated as C.
The formula for determining the number of possible combinations looks like this: (image)
Eventually, cyphers with a number of permutations which are too high become computationally infeasible. But that doesn’t meant their invincible.
Attacks such as frequency analysis exploit the knowledge that some letters in a given sample of plaintext are more common than others. You can cut some corners and make educated guesses about ranges of permutations you don’t need to try, based on statistics.


Poe apparently wrote a book about encryption, which I wasn’t expecting. “The Gold Bug”
Using frequency analysis, the protagonist determines that the most common letter in English is E, and the most common word is The. If you begin by making those two assumptions, you can begin to brute force a simple substitution cypher within a more narrow keyspace.

Breaking classical encryption is possible if you have:
When you know the encryption algorithm, obv.
When there is data about the statistical properties of the encrypted plaintext (so again, letter frequency you can make assumptions about
If you have a large number of encrypted examples.

Theoretically unbreakable, secure encryption using the Vernam cypher requires generating a random number to use as a “pad”, added to the plaintext.
A pad is a key which is as long as the plaintext and is used only once before being discarded.

On Vernam cipher:
First example of this was invented by Gilbert Vernam in 1917.
Was determined to be mathematically unbreakable in 1949 by Claude Shannon, remember that dork?
Difficulty in distributing that one-time key, plus the rapidly bloated length of longer messages, makes this impractical to use.
Fun fact: If you mess up and use the same pad twice, that keystream is known as a “depth” and can be used to cancel out your encryption.
This goof is what allowed the US military to intercept and read German messages generated by a Lorenz machine during WWII.


Modern encryption methods operate in base 2; that is to say, binary. This makes them language-agnostic. Another word for this is a “bitwise operation”.
A single binary digit (1 or 0) is called a bit. Okay, y’all work in software, you knew this already.
A byte is composed of 8 bits. Read in groups of 4, they are called the higher and lower order bits, respectively.

You’re not gonna get out of learning hexadecimal.

Types of operations are confusing to me.
XOR operations, or exclusive OR is used here. Let’s focus on that one.

Symmetric Key (or shared/secret key cryptography) is a modern type of encryption.
When an algorithm uses the same key for both encryption and decryption.
A shared private key, held by the sender and recipient, is used for both and is secure as long as no third party has access  to it.
In order for this to remain secure, each two individuals needs a unique shared key. Therefore, as you add individuals, the number of keys needed scales very quickly.
Two people need one key.
Three people need three
Four people need six, etc.
There’s a formula to calculate this. (attached)
This is great and all but again, distribution of the key is really difficult. If the wrong person gets it, it’s useless.
So shared-key algorithms have these traits:
Care must be taken how the key is stored and exchanged
It’s pretty fast so you can send Moby Dick or whatever if you want to
Not recommended for large groups of users.

Stream Cipher (symmetric key algorithm 1)
Encodes each bit individually or in succession.

Block Cipher (symmetric key algorithm 2)
Breaks plaintext in sections of uniform length, sort of like what we were doing with the polyalphabetic ciphers. Those chunks are called blocks and are encrypted one at a time.




Public-key cryptography
Uses two keys, a shared key which everyone has, and a private key that only one person has.


———————————————————

From Chaz:

Symmetric vs Asymmetric Encryption scheme (or algorithm) in relation to quantum computing

Grover's algorithm - halves symmetric key size
Shor's algorithm - REDACTED (catastrophically reduces) asymmetric key size
