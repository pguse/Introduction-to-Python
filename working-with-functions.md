# Working with Functions

The way in which functions work in Python is similar to the way a computer works.  Both the functions found in software and computer hardware in general can be described using an** INPUT-PROCESSING-OUTPUT** model.

![](/assets/inputOutputDrawing.png)

A computer takes some sort of **data **\(numbers, strings, images, video\) as **INPUT**, performs some sort of **PROCESSING **on the data \(calculations involving numbers, modifying text in an email, editing pixels in an image\), and then produces some sort of **OUTPUT **\(text/graphics on the screen, a new file or email\).  A function in Python acts in much the same way, except that it _**may/may not**_ take **INPUT **and it _**may/may not**_ produce an **OUTPUT**.

To create and implement a function in Python, two steps need to be taken.  First it must be defined using the keyword **def**.

### Function Definition

An example of a function definition in Python is

```
def cube(n):
    return n*n*n
```

**In general** a function definition takes the form

```
def functionName( parameters ):
    statement
    statement
    statement
    return someValue
```

which consists of the **name **of the function, **parameters **_\(separated by commas\)_** **that may/may not be used as **INPUT **to the function, and then statements that are indented as they are in a loop or if statement.  Finally, a value may/may not be returned as the **OUTPUT **of the function.  This is simply the definition of the function.  

### Function Implementation

In order to implement the function we must use the function name, pass in the parameter values as **INPUT**, and possibly assign the **OUTPUT **value to a variable.  The function above could be used in either of the following ways, both producing an output value of 64.

```
value = cube(4)
print( value )
```

or

```
print( cube(4) )
```

Using a **INPUT-PROCESSING-OUTPUT** model, here is what is happening with the _**cube\(\)**_ function.

![](/assets/inputOutputFunctionDrawing.png)

