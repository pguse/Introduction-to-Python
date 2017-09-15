# Working with Data

## Data Types:

There are a number of data types in Python that represent types of information that a variable can store. Here are a few examples:

### Integers:

* a data type in Python that stores an integer such as: -5, 0, 6, 143, -1745

* Assignment Statement - Example: **age = 43**

### 

### Floats:

* a data type in Python that stores a decimal value such as: 3.14, -2.71828

* Assignment Statement - Example: **price = 4.99**

### Strings:

Strings are sequences of letters and numbers, or in other words, chunks of text. They are surrounded by two quotes. The part inside the quotes "" is a string literal, meaning that it should be literally copied and not interpreted as a command.

* a data type in Python that stores text

* each character is stored using an index value

* Assignment Statement - Example: **lastName = "Guse"**

* Find the length of String \(\# of characters including spaces\) using the len\(\) function:  Example: **len**\(lastName\) has a value of 4

```
>>> lastName = "Guse"
>>> print lastName
Guse
>>> print lastName[0]
G
>>> print lastName[3]
e
>>> print len(lastName)
4
```

### Booleans:

The values **True** and **False** are called Boolean values. They often result as the value of a conditional expression, even if you don't explicitly see them. See them in action by looking at the following examples in the interactive python shell

```
>>> print 5 < 10
False
>>> x = 15
>>> print x == 15
True
>>> print 5 < 10
False
>>> x = 15
>>> print x == 15
True
```

They can be used in conditional statements such as **if/elif/else**.

```
paid = True
if paid:
    print "Thank you for paying your bill."
else:
    print "Please pay what you owe."
```

### 

### Tuples

A tuple can store strings, integers, and other data types. Here is an example:

```
>>> myPoint = (3,4)
>>> print myPoint[0]
3
>>> print myPoint[1]
4
>>> myPoint = (3,4)
>>> print myPoint[0]
3
```



