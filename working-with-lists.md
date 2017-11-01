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

As with strings, the **index **of the **element **at the beginning of the list is **0** and increases by 1 as you move across the list.  Also, the code

```
print( len( marks ) )
```

outputs the **length** of the list

```
8
```

as with strings.

## Differences between Strings and Lists

* Strings contain a sequence of characters, whereas **lists **can contain a **mixture of different data types** \(integers, floats, strings, booleans, lists, etc.\).  For example,

`info = [ "Mr. Guse", 47, "Albert College", ["Calculus", "Advanced Functions", "Computer Science", "Physics"] ]`

* Strings are **immutable **- characters cannot be replaced in a string using the index.  **Lists are mutable** - elements can be replaced with other values \(and rearranged\).  For example,

```
info[1] = 48
```

will change the second element of the **list **above.  However, the following code involving a **string **would generate an error.

```
name = "albert college"
name[0] = "A"
```

## Why Use Lists?

Lists are used when you want to **store a sequence of values** in memory, so that they can be **used later** in a program and **modified** if necessary.

## How do you Create a List?

* Assign the initial values of a list to a variable in your program

```
marks = [75, 91, 82, 70, 88, 77, 90, 86]
```

* **Use a loop** to assign values to a list.  For example, you may want the user to enter multiple values into a list.  For example,

```
marks = []                              # An empty list
for i in range(8):
    n = int( input("Enter a mark: ") )
    marks.append(n)                     # append() is a list method that appends values to an existing list
```

* **Use a generator**.  Generators are expressions that allow you to fill a list according to a formula. The general form of a generator is as follows:

  ```
  [ expression for variable in sequence ]
  ```

  where`variable`_is the ID of some variable,_`sequence`_is a sequence of values, which takes the variable \(this can be a list, a string, or an object obtained using the function_`range`_\),_`expression`\_ — some expression, usually depending on the variable used in the generator. The list elements will be filled according to this expression.  

Here are some **examples** of using a **generator**,

```
a = [ i**2 for i in range(5) ]
print(a)
```

produces a list of **squared whole numbers** from 0 to 4.

```
[0, 1, 4, 9, 16]
```

 **or**

```
b = [ 2*i for i in [-5, 3, 11, 15] ]
print(b)
```

 produces a list that has elements which are **double the values** from the initial list

```
[-10, 6, 22, 30]
```

 **or**

```
c = [ int(i) for i in [ '3', '6', '9', '11'] ]
```

 produces a list of **integer** values converted from the initial list of **strings**.



* **Use the \* operator** to **repeat** a set of values in an existing list.  For example,

```
a = [0] * 5
print(a)
```

produces a list containing 5 zeros, which may act as initial values.

```
[0, 0, 0, 0, 0]
```

## How do you read values from a List?

If you want to scan through all of the values \(elements\) in a list, a **for-loop** can be used in two different ways.

#### Example \#1:  Without the range\(\) function

```
for value in [4, 3, -6, -8]:
    print(value, end=":")
```

 produces the **output**

```
4:3:-6:-8
```

#### Example \#2:  Using the range\(\) function, an index and len\(\)

```
    a = [4, 3, -6, -8]
    for i in range( len(a) ):
         print(a[i], end=":")
```

 produces the **output**

```
4:3:-6:-8
```

The **advantage** of this method is that the variable **i** keeps track of the **position** \(index\) of each **element** in the list.  This index information is important in certain situations and problems.

## Converting a String to a List using split\(\)

Often in programs you want to convert a string into a list especially when getting data input from the keyboard or from a file.  For example,

```
a = "75 91 82 70 88 77 90 86"
b = a.split()
print(b)
```

produces the **output**

```
['75', '91', '82', '70', '88', '77', '90', '86']
```

where the **split\(\)** function uses the spaces to separate the string into a list of strings.  Now, in this situation we probably want to **convert** each **element** in the list to an **integer**.  This can be done using a **generator** _\(described above\)_ as follows:

```
c = [ int(value) for value in b ]
print(c)
```

This produces the **output**

```
[75, 91, 82, 70, 88, 77, 90, 86]
```

#### Example: Input from the Keyboard

You can input multiple values from the keyboard using the following code:

```
a = input("Enter your marks: ")            # Input a single string
b = a.split()                              # Convert the string to a list of strings
c = [ int(value) for value in b ]          # Create a list of integers from a list of strings
print(a)                                   # Output the single string
print(b)                                   # Output the list of strings
print(c)                                   # Output the list of integers
```

Here is an example of how this could run:

```
>>Enter your marks:  75 91 82 70 88 77 90 86
'75 91 82 70 88 77 90 86'
['75', '91', '82', '70', '88', '77', '90', '86']
[75, 91, 82, 70, 88, 77, 90, 86]
```

This can also be done in a single line as follows:

```
marks = [ int(value) for value in input().split() ]
```

where **input\(\)** returns a single string, **split\(\)** then returns a list of strings, and then the **generator** returns the list of integers.

