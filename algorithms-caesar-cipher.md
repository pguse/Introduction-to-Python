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

#### Method \#1:  Using the String method find\(\)

The string method **find\(\)** returns the **index **of the first occurrence of the **letter **you provide as an **argument**, in the **string **you run the method on.  For example, the code

```
alphabet.find('T')
```

has the value **19 **\(count the letters in _alphabet_ yourself, starting at zero\).  We want to add 3 to this position, to move down the alphabet 3 steps.  So, the code

```
alphabet.find('T') + 3
```

has the value **22**.  To produce the appropriate **letter **in the alphabet at position **22**, we must use this value as the **index **of the string identifier _alphabet_.  This is done using the expression

```
alphabet[ alphabet.find('T') + 3 ]
```

which is equivalent to the expression

```
alphabet[22]
```

which has the value **W**.  This is actually the letter that we want to add to the string identifier **cipher**.  So we need to use an expression like

```
cipher = cipher + alphabet[ alphabet.rfind('T') + 3 ]
```

Our codethen becomes,

```
cipher = ""
for i in range( len(plainText) ):
    cipher = cipher + alphabet[ alphabet.rfind('T') + 3 ]
```

except the letter we want to encode is not always a _'T'_.  The letters we want to encode are represented by the expression

```
plainText[i]
```

where _plainText\[0\] = 'T'_', and _plainText\[1\] = 'H'_, and _plainText\[2\] = 'E'_, etc.  So, our final version of the code to create the correct cipher is

```
cipher = ""
for i in range( len(plainText) ):
    cipher = cipher + alphabet[ alphabet.rfind( plainText[i] ) + 3 ]
```

The output of _**print\(cipher\)**_ will be \(see **IMPORTANT NOTE** below\)

```
WKHTXLFNEURZQIRAMXPSVRYHUWKHODCBGRJ
```

#### Method \#2:  Using nested for-loops

Remember, to pass through the indices of the _plainText_ string we can use a** for-loop**.

```
cipher = ""
for i in range( len(plainText) ):
    cipher = cipher + plainText[i]
```

But for each letter we want to pass through the string \_alphabet \_and look for the **same letter**.  We can do this using another** for-loop** and an** if-statement** as follows

```
cipher = ""
for i in range( len(plainText) ):
    for j in range( len(alphabet) ):
        if plainText[i] == alphabet[j]:
            cipher = cipher + alphabet[j+3]
            break
```

Once we find the **same letter** in the string _alphabet_, we add the character in _alphabet \_3 steps down from the current position to \_cipher_.  The use of the statement **break **stops the inner loop from executing once we find the appropriate letter.

The output of _**print\(cipher\)**_ will be \(see **IMPORTANT NOTE** below\)

```
WKHTXLFNEURZQIRAMXPSVRYHUWKHODCBGRJ
```

#### IMPORTANT NOTE:

Both methods described above have a** terrible flaw**.  If the letter we are looking at is near the end of the alphabet, **adding 3 ** to its position might take us past the end of the _alphabet_ string \(for example: X, Y, or Z\).  We can fix this by simply doubling the length of the \_alphabet \_string as follows:

```
alphabet = "ABCDEFGHIJKLMNOPQRSTUVWXYZABCDEFGHIJKLMNOPQRSTUVWXYZ"
```

This guarantees that for **any shift less than 26**, we will not move beyond the end of the string _alphabet_.

#### What about Spaces and Punctuation?

The string method _**isalpha\(\)**_ checks whether a string contains only alphabetic characters or not.  For example, the expression

`"Albert College".isalpha()`

has a value

`False`

because of the space, whereas the expression

`"Albert".isalpha()`

has a value

`True`

This expression can be used in an **if-statement** to perform different actions on alphabetic or non-alphabetic characters.  To maintain the spaces and punctuation in our cipher we can use the following code.

```
cipher = ""
for i in range( len(plainText) ):
    if plainText[i].isalpha():
        for j in range( len(alphabet) ):
            if plainText[i] == alphabet[j]:
                cipher = cipher + alphabet[j+3]
                break
    else:
        cipher = cipher + plainText[i]
```

The output of _print\(cipher\)_ will now be

```
WKH TXLFN EURZQ IRA MXPSV RYHU WKH ODCB GRJ
```



