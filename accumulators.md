# Using Accumulators

An accumulator is a variable that is used in a loop to construct a value using an iterative process.  It could act like a counter using addition, or perform exponentiation through repeated multiplication, or built a string character by character.  Here are some examples of accumulators in action.

## The Sum of all Integers

The act of adding consecutive integers e.g. 0 + 1 + 2 + 3 + 4 + 5 + ... can be thought of as an iterative process.  In each step you are adding - the only thing that changes is the number being added.  In Python, this can be done using a loop, as follows:

> N = 5
>
> s = 0
>
> for i in range\(1, N+1\):
>
>     s = s + i
>
> print

The result \(15\) that is printed is the sum of all integers between 1 and 5.  Here is a table that summarized how each variable changes values are the loop iterates.

| N | i | s |
| :---: | :---: | :---: |
| 10 | - | 0 |
| 10 | 1 | **1** |
| 10 | **2** | **3** |
| 10 | 3 | 6 |
| 10 | 4 | 10 |
| 10 | 5 | 15 |

The assignment statement **s = s + i** is the key line and most importantly it is read from right-to-left.  The current values of **s** and **i** are added together and the result stored back in the variable/identifier called **s**.  In the table above one of these calculations is shown using the bolded values, where **i** and **sum** have the values 2 and 1.  They are added to given the new value of **s**, which is 3.

The code above can be packaged as a function to make it easier to use.  For example:

| def sum\(N\): |
| :--- |
| s = 0 |
| for i in range\(1,N+1\): |
| s = s + i |
| return s |

So, running the function at the interactive prompt would look like the following:

&gt;&gt; sum\(5\)

15

&gt;&gt; sum\(3\)

6

## Factorials



