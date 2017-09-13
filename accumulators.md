# Using Accumulators

An accumulator is a variable that is used in a loop to construct a value using an iterative process.  It could act like a counter using addition, or perform exponentiation through repeated multiplication, or built a string character by character.  Here are some examples of accumulators in action.

## The Sum of all Integers

The act of adding consecutive integers e.g. 0 + 1 + 2 + 3 + 4 + 5 + ... can be thought of as an iterative process.  In each step you are adding ... the only thing that changes is the number being added.  In Python, this can be done using a loop, as follows:

```
N = 5
s = 0
for i in range(1, N+1):
    s = s + i
print s
```

The result \(15\) that is printed is the sum of all integers between 1 and 5.  Here is a table that summarizes how each variable changes values are the loop iterates.

| N | i | s |
| :---: | :---: | :---: |
| 10 | - | 0 |
| 10 | 1 | **1** |
| 10 | **2** | **3** |
| 10 | 3 | 6 |
| 10 | 4 | 10 |
| 10 | 5 | 15 |

The assignment statement **s = s + i** is the key line and most importantly it is read from **right-to-left**.  The current values of **s** and **i** are added together and the result stored back in the variable/identifier called **s**.  In the table above one of these calculations is shown using the bolded values, where **i** and **sum** have the values 2 and 1.  They are added to give the new value of **s**, which is 3.

The code above can be packaged as a function to make it easier to use.  For example:

```
def sum(N):
    s = 0
    for i in range(1, N+1):
        s = s + i
    return s
```

So, running the function at the interactive prompt would look like the following:

&gt;&gt; sum\(5\)

15

&gt;&gt; sum\(3\)

6

In these examples, the values 5 and 3 act as inputs to the function.  They represent the maximum integer to be added.  The returned value \(15 and 6\) are the sums of the integers \(from 1 to 5 **or** from 1 to 3\).

## Sum of all Even Integers

Similar to the problem above, we can create a function that adds all even integers up to \(and including\) a given maximum value N.  For example,

```
def sumEven(N):
    s = 0
    for i in range(1, N+1):
        if i % 2 == 0:
            s = s + i
    return s
```

Here we have included a conditional statement, where the sum is only modified when we encounter and even value of **i**.  The expression,  **i % 2 == 0** , checks whether the remainder of **i**  divided by 2 is zero.  If it evaluates to **True**, **i** must be even and should be added to the sum **s**.  The symbol** %** is called the **modulus** operator.

So, running the function at the interactive prompt would look like the following:

&gt;&gt; sumEven\(4\)

6

&gt;&gt; sumEven\(10\)

30

## Factorial

A factorial is a specific type of repeated multiplication.  For example, 4! = 4x3x2x1 = 24, where 4! is read as 'four factorial'.  This can be computed using repeated multiplication.  For example,

```
def factorial(N):
    f = 1
    for i in range(1, N+1):
        f = f * i
    return f
```

So, running the function at the interactive prompt would look like the following:

&gt;&gt; factorial\(4\)

24

&gt;&gt; factorial\(5\)

120

