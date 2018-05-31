# Algorithms - Recursion

A definition or function is recursive if it refers to itself.  To be well-founded, a recursive definition must meet two properties:

* There must be one or more base cases that require no recursion.
* All chains of recursion must eventually reach a base case.

A simple way to guarantee these conditions is for recursive calls to always be made on smaller versions that can be solved directly.  Sequences can be considered recursive structures containing a first item followed by the rest of the sequence. Recursive functions can be written following this approach.  Recursion is more general than iteration. Choosing between recursion and looping involves the considerations of efficiency and elegance.
