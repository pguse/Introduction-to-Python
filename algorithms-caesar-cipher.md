# Algorithms - Caesar Cipher

_“In cryptography, a Caesar cipher, also known as Caesar's cipher, the shift cipher, Caesar's code or Caesar shift, is one of the simplest and most widely known encryption techniques. It is a type of sustitution cipher in which each letter in the plaintext is replaced by a letter some fixed number of positions down the alphabet. For example, with a shift of 3, A would be replaced by D, B would become E, and so on. The method is named after Julius Caesar, who used it in his private correspondence.” ~ Wikipedia_

| ![](/assets/320px-Caesar3.png) |
| :---: |


Let's try to encode, in **Python**, a **Caesar Cipher** with a shift of 3 on the string "THE QUICK BROWN FOX JUMPS OVER THE LAZY DOG".  First, label the string with the identifier _plainText_.

```
plainText = "THE QUICK BROWN FOX JUMPS OVER THE LAZY DOG"
```

The goal is to replace each letter in the _plainText_ string with a letter that is 3 steps down the alphabet.  So, our program needs to store the alphabet so that this information can be used.  This can be done using another string identified by_ alphabet_.

```
alphabet = "ABCDEFGHIJKLMNOPQRSTUVWXYZ"
```

Here are the steps that we are going to follow to create the cipher.

**STEP \#1:**

Look at the first letter in the _plainText_ string

**STEP \#2:**

Look for the posiiton of this letter in the _alphabet_ string and add 3 to this position

**STEP \#3:**

Add the letter at the new position \(3 steps down the alphabet\) to the existing cipher.  **Note:** The initial cipher will be an empty string "".

**STEP \#4:**

Go back to **STEP \#1**, look at the next letter, and go to **STEP\#2**.  Note:  This

### The Encoding:  Python Code

To pass through the indices of the _plainText_ string we can use a** for-loop**.

```
cipher = ""
for i in range( len(plainText) ):
    cipher = cipher + plainText[i]
```

Letter by letter, this **for-loop** adds each letter from _plainText_ to the string identifier _cipher_, which begins as an empty string.  This code fragment does not do exactly what we want, but demonstrates how we can build cipher letter by letter.  At the moment, the statement

```
print(cipher)
```

produces the output

```
THE QUICK BROWN FOX JUMPS OVER THE LAZY DOG
```

We now need to shift each letter down the alphabet 3 steps, before we add it to _cipher_.  This can be done a couple ways:

#### Method \#1:  Using the String method rfind\(\)

The string method **rfind\(\)** returns the **index **of the first occurrence of the letter you provide as an argument, in the string you run the method on.  For example, the code

```
alphabet.rfind('T')
```

has the value **19 **\(count the letters in the alphabet yourself, starting at zero\).  We want to add 3 to this position, to move down the alphabet 3 steps.  So, the code

```
alphabet.rfind('T') + 3
```

has the value **22**.  To produce the appropriate letter in the alphabet at position 22, we must use this value as the **index **of the string identifier _alphabet_.  This is done using the expression

```
alphabet[ alphabet.rfind('T') + 3 ]
```

which is equivalent to the expression

```
alphabet[22]
```

which has the value **W**.  This is actually the letter that we want to add to the string identifier _cipher_.  So we need to use an expression like

```
cipher = cipher + alphabet[ alphabet.rfind('T') + 3 ]
```

So our code above becomes,

```
cipher = ""
for i in range( len(plainText) ):
    cipher = cipher + alphabet[ alphabet.rfind('T') + 3 ]
```

except the letter we want to encode is not always a _'T'_.  The letters we want to encode are represented by the expression

```
plainText[i]
```

where _plainText\[0\] = "T"_, and _plainText\[1\] = 'H'_, and _plainText\[2\] = 'E'_, etc.  So, our final version of the code to create the correct cipher is

```
cipher = ""
for i in range( len(plainText) ):
    cipher = cipher + alphabet[ alphabet.rfind( plainText[i] ) + 3 ]
```



