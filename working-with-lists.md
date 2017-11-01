# Working with Lists

**Lists **consist of a **sequence** of elements. Each element is accessed using an **index **value, as you access characters in a string.  For example,

`marks = [75, 91, 82, 70, 88, 77, 90, 86]`

**Notice **the square brackets and that the **elements **in the list are separated by commas. The following program

```
print( marks[0] )
print( marks[7] )
print( marks[3] )
```

produces the output

```
75
86
70 
```

As with strings, the **index **of the **element **at the beginning of the list is 0 and increases by 1 as you move down the list.  Also, the code

```
print( len( marks ) )
```

outputs the length of the list

```
8 
```

as with strings.

## Differences between Strings and Lists

* Strings contain a sequence of characters, whereas **lists **can contain a **mixture of difference data types** \(integers, floats, strings, booleans, lists, etc.\).  For example,

`info = [ "Mr. Guse", 47, "Albert College", ["Calculus", "Advanced Functions", "Computer Science", "Physics"] ]`

        is a list that contains a number of different data types.

* Strings are **immutable **- characters cannot be replaced in string using the index.  **Lists are mutable** - elements can be replaced with other values and rearranged.  For example,

```
info[1] = 48
```

will change the second element of the **list **above.  However, the following code involving a **string **would generate an error.

```
name = "albert college"
name[0] = "A"
```

## Creating a List

* Assign a list to a variable in your program

```
marks = [75, 91, 82, 70, 88, 77, 90, 86]
```



