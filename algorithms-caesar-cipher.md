# Algorithms - Caesar Cipher

_“In cryptography, a Caesar cipher, also known as Caesar's cipher, the shift cipher, Caesar's code or Caesar shift, is one of the simplest and most widely known encryption techniques. It is a type of sustitution cipher in which each letter in the plaintext is replaced by a letter some fixed number of positions down the alphabet. For example, with a shift of 3, A would be replaced by D, B would become E, and so on. The method is named after Julius Caesar, who used it in his private correspondence.” ~ Wikipedia_

| ![](/assets/320px-Caesar3.png) |
| :---: |


Let's try to encode, in Python, a Caesar Cipher with a shift of 3 on the string "THE QUICK BROWN FOX JUMPED OVER THE LAZY DOG".  First, label the string with the identifier _plainText_.

```
plainText = "THE QUICK BROWN FOX JUMPS OVER THE LAZY DOG"
```

The goal is to replace each letter in the _plainText_ string with a letter that is 3 steps down the alphabet.  So, our program needs to store the alphabet so that this information can be used.  This can be done using another string identified by_ alphabet_.

```
alphabet = "ABCDEFGHIJKLMNOPQRSTUVWXYZ"
```

Here are the steps that we are going to follow to create the cipher.

STEP \#1:

Look at the first letter in the plainText string

STEP \#2:

Look for the posiiton of this letter in the alphabet string and add 3 to this position

STEP \#3:  

Add the letter at the new position \(3 steps down the alphabet\) to the existing cipher.  Note: The initial cipher will be an empty string "".

