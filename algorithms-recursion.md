# Algorithms - Recursion

A definition or function is recursive if it refers to itself.  To be well-founded, a recursive definition must meet two properties:

* There must be one or more base cases that require no recursion.
* All chains of recursion must eventually reach a base case.

A simple way to guarantee these conditions is for recursive calls to always be made on smaller versions that can be solved directly.  Sequences can be considered recursive structures containing a first item followed by the rest of the sequence. Recursive functions can be written following this approach.  Recursion is more general than iteration. Choosing between recursion and looping involves the considerations of efficiency and elegance.

Here are some examples of recursive functions:

## Factorial

A factorial can be defined in terms of a factorial.  This is a recursive definition.  For example:

4! = 4 x 3 x 2 x 1

can be written as:

4! = 4 x 3!

This can be coded in Python as follows:

```
def factorial(n):
  if n == 1:
     return 1
  else:
     return n * factorial(n-1)
```

where n = 1 is the base case.

## Sum of Consecutive Integers

A sum of consecutive integers can be defined in terms of a sum.  Again, this is recursive.  For example:

4 + 3 + 2 + 1

can be written as:

4 + (3 + 2 + 1)

This can be coded in Python as follows:

```
def sum(n):
  if n == 1:
     return 1
  else:
     return n + sum(n-1)
```

where n = 1 is the base case.

## Sum of Elements of a List

The sum of elements of a list can be defined as the sum of the nth element plus the sum of the first n-1 elements.  For example:

Sum of [4, 9, 3, 5] = Sum of 5 + Sum of [4, 9, 3]

This can be coded in Python as follows:

```
def sumOfList(n):
   if len(n) == 1:
      return n[0]
   else:
      return n[len(n)-1] + sumOfList(n[:-1])
```
