# Algorithm Efficiency:  Big O Notation

## Example:  Selection Sort - Efficiency

The selection sort involves scanning the list from the beginning to find the position of the **minimum value**, then placing the minimum value at the **beginning of the list**, by **swapping the two values**. This is **repeated **by **starting at the next position** in the list. The minimum value is found in the remainder of the list and the two values are swapped. Repeat until you have passed through the entire list.

So, the first time through the **list of length 7**, you must compare/check **6 values**

| 0 | 1 | 2 | 3 | 4 | 5 | 6 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| 76 | 10 | 5 | -17 | 34 | 25 | 2 |

The second time **5 values** are checked/compared,

| 0 | 1 | 2 | 3 | 4 | 5 | 6 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| -17 | 10 | 5 | 76 | 34 | 25 | 2 |

Then, **4 values** are checked, and so on ...

| 0 | 1 | 2 | 3 | 4 | 5 | 6 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| -17 | 2 | 5 | 76 | 34 | 25 | 10 |

The total number of comparison equals 6 + 5 + 4 + 3 + 2 + 1 = **21 comparisons**. For a general list containing n items. The number of comparisons is


$$
1+2+3 +...+n-1 = { n(n-1) \over 2}
$$


It turns out that in general, the number of comparisons equals $${n(n-1) \over 2}$$ for a list of size n. So, for our list of size 7,** 7\(6\)/2 = 21 **comparisons. When we are analyzing efficiency, we are really just concerned **how the number of steps/comparisons changes as n becomes large**. Since,


$$
{n(n-1) \over 2} = {1 \over 2} n^2 - {1 \over 2} n
$$


For large n, the $$n^2$$ term dominates this expression, so the \(worst-case\) efficiency of the selection sort is described by** O\(**$$n^2$$**\). **Similarly, both the **bubble sort and the insertion sort** are considered** O\(**$$n^2$$**\) **algorithms or **quadratic**.

## Other Algorithms - Efficiency

The** linear search** on a list of **length n** must in the **worst-case** search through **n items**.  As a result, its efficiency is described by **O\(n\)** or** linear**.  In comparison, the **binary search** has an efficiency described by** O\(**$$logn$$**\)**, because it takes a number of steps based on $$log(n)$$ on a list of length n.  For example, in a **sorted list of length 100**, it takes a maximum number of steps equal to $$log_2 (100) = 6.64 ~= 7$$.

The efficiency of an algorithm can be visualized by looking at graphs of the functions $$y=x$$, $$y=x^2$$, and $$y=log(n)$$.  In general, a _linear** **_**O\(n\)** algorithm is** 'slower'** than a _quadratic_ algorithm** O\(**$$n^2$$**\)** which is** 'slower'** than a _logarithmic_ O\($$logn$$\) algorithm for large values of n.

![](/assets/algorithmEfficiency.png)

