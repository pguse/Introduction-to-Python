# Working with Functions

The way in which functions work in Python is similar to the way a computer works.  Both the functions found in software and computer hardware can be described using an** INPUT-PROCESSING-OUTPUT** model.

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
def functionName(parameters):
    statement
    statement
    statement
```



