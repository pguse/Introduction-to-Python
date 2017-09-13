# Accumulators - Part 2

## Palindromes

A palindrome is a word or phrase that reads the same when read forwards or backwards.  A function using an accumulator can be created that will return a palindrome constructed from a given input word.  For example, palindromize\("abc"\) -&gt; "abcba".  This example is similar to the reverse\(\) function described in Part 1.  The main difference is we will not be starting with an empty string, but instead the word itself.  Here are some key ideas to remember:

* range\(start, end, s\) generates a list from **start **to **end **in steps of size **s**, not including the value of end

* if the values increase from **start **to **end**, **s **is positive, otherwise for decreasing values **s **is negative

* **len**\(word\) calculates/return the length of a string called **word**.
* the characters of a string are accessed using an index:  **word\[0\]** is the first character, **word\[1\]** the second character, ... **word\[len\(word\)-1**\] is the last character  \(because the index starts at zero\).
* strings or characters are combined together using the **'+'** operator.  This is called **concatenation**.
* To build a string character by character using an accumulator, you would use the following code,

```
word = "albert"
accumulator = ""
for i in range(len(word)):
    accumulator = accumulator + word[i]
print accumulator
```

The output of this code would be:   albert

## Exponentiation

Using an exponent is really just a short form for repeated mulitiplication so exponentiation ca

## Answers

### Palindrome

```
def palindromize(word):
	new_string = word
	for i in range(len(word)-2, -1, -1):
		new_string = new_string + word[i]
	return new_string
```



