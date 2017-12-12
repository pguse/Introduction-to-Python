# Algorithm Efficiency:  Big O Notation

## Example:  Selection Sort - Efficiency

The selection sort involves scanning the list from the beginning to find the position of theminimum value, then placing the minimum value at the beginning of the list, by swapping the two values. This is repeated now starting at the next position in the list. Find the minimum value in the remainder of the list and swap the two values. Repeat until you have passed through the entire list.

So, the first time through the list, of length 7, you must compare/check 6 values

| 0 | 1 | 2 | 3 | 4 | 5 | 6 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| 76 | 10 | 5 | -17 | 34 | 25 | 2 |

The second time 5 values are checked/compared,

| 0 | 1 | 2 | 3 | 4 | 5 | 6 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| -17 | 10 | 5 | 76 | 34 | 25 | 2 |

Then, 4 values are checked, and so on ...

| 0 | 1 | 2 | 3 | 4 | 5 | 6 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| -17 | 2 | 5 | 76 | 34 | 25 | 10 |

The total number of comparison equals 6 + 5 + 4 + 3 + 2 + 1 = 21 comparisons. For a general list containing n items. The number of comparisons is

$$1+2+3 +...+n-1 = { n(n-1) \over 2}$$

It turns out that in general, the number of comparisons equalsn\(n-1\)2for a list of size n. So, for our list of size 7, 7\(6\)/2 = 21 comparisons. When we are analyzing efficiency, we are really just concerned how the number of steps/comparisons changesas n becomes large. Since,

n\(n-1\)2=12n2-12n

For large n, the n2term dominates this expression, so the \(worst-case\) efficiency of the selection sort is described byO\(n2\). Similarly, the both the bubble sort and the insertion sort are considered O\(n2\) algorithms.
