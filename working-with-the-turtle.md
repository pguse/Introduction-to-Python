# Working with the Turtle

A computer program is just a series of **instructions** given to a computer to perform.  Here is an example of a program in Python that uses the turtle module.

```
import turtle

# Creating a turtle object as defined in the turtle module imported above

tina = turtle.Turtle()

# Turtle objects have associated functions that either set properties of the turtle or move the turtle.
# Here we set three turtle properties

tina.shape('turtle')
tina.width(2)
tina.color('blue')

# Definition of the square() function
# Instructs the turtle how to draw a square

def square():
  tina.forward(100)
  tina.right(90)
  tina.forward(100)
  tina.right(90)
  tina.forward(100)
  tina.right(90)
  tina.forward(100)
  tina.right(90)

square()
```

Notes:

* To use the turtle module it must first be imported as done on the first line using the **import** command.
* All lines beginning with **\#** are comments.  _These are not read by the Python interpreter._
* The variable **tina** is an example of an **object** \(of type Turtle\).  The turtle module provides different **properties** that can be set for turtle objects.  For example:  shape, width, and color.  Notice the use of the **dot** \(operator\) when assigning these properties.  The turtle module also provides different **methods**/actions that the turtle can perform.  For example: forward, and right.  Again, notice the use of the **dot** when implementing these **methods**.
* The line **def** square\(\) gives a name to our sequence of instructions that move the turtle.  In order to run these instructions, we must type square\(\) ... this is called a **function** in Python.





