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

Write a function called **palindromize\(word\)** that takes in a string called **word **as input and outputs/returns a palindrome as in the example above.  A couple hints:

* The initial value of the accumulator should be **word**.
* You should begin by adding the second last character of **word **to the accumulator and finish with the first character of **word**

## Exponentiation

Using an exponent is really just a short form for repeated mulitiplication so exponentiation can be thought of as an iterative process using an accumulator.  For example:

$$ 2^5 = 2 \times 2 \times 2 \times 2 \times 2$$

Write a function called **exp\(x,n\)** that takes in a base **x **and exponent **n **and outputs/returns x^n

Here are some key ideas to remember:

* The exponent indicates the number of iterations that the loop must make
* The initial value of the accumulator should be 1 - just like in the factorial\(\) example in Part 1

## Babylon Square Root

There are different methods/algorithms that you can use to calculate a square root without using a calculator.  The Babylon Square Root method is one of the Say we are trying to find the square root of N. Just like with the guess and check method, we start out with some guess R. Then we compute a new value for R as follows:

!\[\]\([https://s0.wp.com/latex.php?latex=\displaystyle+R'+%3D+\frac{R+%2B+N%2FR}{2}.&bg=ffffff&fg=333333&s=0](https://s0.wp.com/latex.php?latex=\displaystyle+R'+%3D+\frac{R+%2B+N%2FR}{2}.&bg=ffffff&fg=333333&s=0) "\displaystyle R' = \frac{R + N/R}{2}."\)

Repeating this process will result in closer and closer approximations to ![](https://s0.wp.com/latex.php?latex=\sqrt{N}&bg=ffffff&fg=333333&s=0 "\sqrt{N}").

## Answers

### Palindromes

```
def palindromize(word):
    new_string = word
    for i in range(len(word)-2, -1, -1):
        new_string = new_string + word[i]
    return new_string
```

### Exponentiation

```
def exp(x,n):
    answer = 1
    for i in range(n):
        answer = answer * x
    return answer
```



