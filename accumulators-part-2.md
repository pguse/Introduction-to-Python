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

Write a function called **exp\(x,n\)** that takes in a base **x **and exponent **n **and outputs/returns $$ x^n $$

Here are some key ideas to remember:

* The exponent indicates the number of iterations that the loop must make
* The initial value of the accumulator should be 1 - just like in the factorial\(\) example in Part 1

## Babylon Square Root

There are different iterative methods/algorithms that you can use to calculate a square root without using a calculator.  The Babylon Square Root method is one of the fastest-converging methods.  Say we are trying to find the square root of **N**. We start out with some guess R. Then we compute a new value for R as follows:


$$
 R_{new} = { {R + {N \over R} } \over 2 }
$$


Repeating this process  \(feeding the new value of R back into the formula as the value R on the right-hand side\) will result in closer and closer approximations to $$ \sqrt N $$.

Write a function called **babylonSqrt\(x, accuracy\)** that takes in a value **x **to take the square root of and the desired accuracy of the answer, and outputs the square root of **N **calculated by the Babylon method of square roots.

Here are some key ideas to remember:

* Use a **while **loop, because you don't know ahead of time how many iterations will be required.
* There is a built-in function in Python called** abs\(\)** that determines the absolute value of a number e.g. **abs**\(-5\) = 5
* If $$ \mid { R_{new} - R } \mid < accuracy $$, then you should break out of the loop using the **break **command
* An example value for accuracy could be 0.001, so the $$ \sqrt N $$ is correct to 2 decimal places.
* The initial value of the **accumulator **is the starting guess for $$ \sqrt N $$, which I would suggest could be N/2.

## Calculating Pi

The Leibniz formula for calculating the value of $$ \pi $$ is


$$
 {   {\pi \over 4} -1 = - {1 \over 3} + {1 \over 5} - {1 \over 7} + ...}
$$


The general term of the series takes the form


$$
 {1 \over (2n+1)} (-1)^n
$$


Write a function called **LeibnizPi\(n\)** that computes $$ \pi $$ according to the Leibniz formula, using **n **terms of the right-hand side series.

Here are some ideas to remember:

* The initial value of the **accumulator **should probably be 1
* Use a **for-loop** since you know that the number of iterations will be **n**.

## Euclid's Algorithm for Greatest Common Divisor \(GCD\)

Euclid's algorithm is a technique for quickly finding the **GCD **of two integers **a **and **b**.  Remember, the **GCD **is the largest integer that divides into both integers **a **and **b**.  Here is how the algorithm works in a table format, assuming **a = 270**  and **b = 192** are the original integers.

| a | b | a % b |
| :---: | :---: | :---: |
| 270 | 192 | 78 |
| 192 | 78 | 36 |
| 78 | 36 | 6 |
| 36 | 6 | 0 |

When **a % b == 0**, then the **GCD **is the current value of **b**.  In this case, the GCD is 6.

Start with the original values of **a **and **b**, and then calculate **a % b**. Now reassign the values so that **a **takes on the old value of **b **and **b **takes on the value of **a % b**.

Here are some ideas to remember:

* When swapping values you often need to temporarily save a value in a different variable so that it doesn't get 'written over'.  In this case, you could use the following code to swap the values

```
swap = a % b
a = b
b = swap
```

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

### Babylon Square Root

```
def babylonSqrt(x,accuracy):
    r = x / 2.0
    while True:
        r_new = (r + x/r) / 2.0
        if abs(r_new - r) < accuracy:
            break
        r = r_new
    return r_new
```

### Calculating Pi

```
def leibnizPi(n):
    pi_over4 = 1
    for i in range(1,n+1):
        pi_over4 = pi_over4 + (-1)**i / (2.0*i + 1)
    return (pi_over4 * 4)
```

### Euclid's Algorithm for Greatest Common Divisor \(GCD\)

```
def gcd(a,b):
    while a % b !=0:
        swap = a % b
        a = b
        b = swap
    return b
```

To experiment with these functions, go to the following [link](https://repl.it/LDvT/14).

