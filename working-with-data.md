# Working with Data

## Data Types

There are a number of data types in Python that represent types of information that a variable can store. Here are a few examples:

### Integers:

* a data type in Python that stores an integer such as: -5, 0, 6, 143, -1745

* Assignment Statement - Example: **age = 43**

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

## Variables

Variables have a type determined by their assignment statement.  For example, in the code

```
score = 4
```

the variable **score **is an integer, because it has been assigned an integer value.  In this code,

```
mark = 87.4
```

the variable **mark **is a float.  Sometimes it is not so obvious.  In the following calculation,

```
total = score * 2 + 5
```

the variable **total **is an integer because only integer values have been used in the calculation.  However, in this code,

```
average = (5 + 6 + 4) / 3
```

the variable **average **is a float because of the division operator_ \(division always produces a float\)_, even though all values in the calculation are integers.  Whereas, in the code

```
hundreds = 563 // 100
```

the variable **hundreds **is an integer because // is the integer division operator.  If you are not sure about the type of a variable you can use the type\(\) function.  For example,

```
>> type(average)
<class 'float'>
>> type(mark)
<class 'int'>
```

## Style and Variable Naming Rules

You cannot use any variable name in Python.  Here are the rules that must be followed.

**The Rules**

* Variables names must **start **with a **letter **or an **underscore**, such as: \_password, my\_password
* The **remainder **of your variable name may consist of **letters**, **numbers **and **underscores**. password1,  n00b. ...
* Names are **case sensitive**. my\_password, MY\_PASSWORD, and My\_Password are each a different variable.

**Style**

* Your variable names should describe what the variable represents, so **a**, **b**, **x**, and **y **are not very good names.  Better names would be **score**, **average**, **name**, etc.
* If you wish to use a combination of names, there are two styles that are common \(since you cannot use spaces in your variable name\).  The underscore character can be used:  **final\_score**, or you can use capitalization: **finalScore**.



