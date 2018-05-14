# Working with Objects

## Introduction

Python works with numbers essentially just like a calculator. When you type:

```
> 1 / 2
0.5
```

it automatically produces a decimal \(float-point\) value. By creating the **Fraction** class, we are going to enable Python to deal with fractions just like we might in an introductory math class. A class acts like a template or blueprint that includes **two features**:

1. **Data**- often called fields or properties

2. **Methods**- what we have so far called functions

The file below \(**fraction.py**\) shows an example of a **Fraction** class. It involves data \(the fields/properties\) that represents the numerator \(**self.a**\) and denominator \(**self.b**\) of a **Fraction**. These values are initialized when the **Fraction** is created - the special Python function **\_\_init\_\_\(self, \_a, \_b\)** , called the constructor, assigns/binds the input values \_a and \_b to the field identifiers/variables \(**self.a** and **self.b**\).

![](https://lh3.googleusercontent.com/g2JJQA8XvfZKJCYG35WrWIQ0tzWO4F5m18CODRL5PXnR1BNFn5FX53lA-iGOQI-6meiAitheED5IqyxjmuhokrVq9XkEziGO-UFTjox1t_F2YwHmgPaXSTxV2hfSI1wtxGrUXRLS)

The other special Python function in this class is

```
__str__(self)
```

It **returns** the **string** that represents a particular **Fraction** when you attempt to print it out.

## What is self ?

The unusual part about classes in Python is the word **self**. In this example, the **Fraction** class represents any fraction. The word **self** refers to the particular fraction you have created with this class. It must be used as the **first argument** in the definition of every method and in the names of each field. Note: The word **self** never occurs when you actually call a **method**.

## How to Use the Class to Create an Object

![](https://lh3.googleusercontent.com/Bqy13Vb24ajiz8cgKBFO7Gv0mzr6RDlqeUp4jdKtJKLFhgxNcb1bpqjNIwumJYfou2_WTe1sjKNo1vQC0mi-WgbgcHQ1c_QRPrh7lRR1hvndnZnbibiAk10HMBNHjg0YYqXFjX47)

Notice how a Fraction is created, using the word **Fraction** \(the name of the class\).

```
f1 = Fraction(1,2)
```

The values input to this method match those in the **\_\_init\_\_** function, because this is the method run when a **Fraction** is created. This is called creating an instance of the **Fraction** class or in other words f1, f2, and f3 are called **objects** of type **Fraction**.

## How to Use the Methods

Notice how the product of two Fractions is calculated.

```
f3 = f1.prod(f2)
```

The dot operator is used to call a method \(eg.prod\) on an object \(eg.f1\) of a class. The definition of the **prod** method is,

```
def prod(self, f):
    return Fraction(self.a * f.a , self.b * f.b)
```

It **returns a Fraction** with a new numerator \(**self.a \* f.a**\) and denominator \(**self.b \* f.b**\). The value **self.a** is the numerator of the calling **Fraction** \(eg. f1 in the example above\), while **f.a** is the numerator of the **Fraction** input to the **prod** function \(eg.f2 in the example above\).

Notice how you could apply two methods to a single **Fraction object**.

```
f1.prod(f2).simplify()
```

The expression

```
f1.prod(f2)
```

produces a new **Fraction** object that the method **simplify\(\)** is then applied to.

## Using External Files:

All the files in this example:  **main.py**, **mymath.py**, and **fraction.py** must be contained in the same folder, after downloading them from moodle. In order to use the Fraction class in **main.py**, the line

```
from fraction import *
```

is necessary. If we had instead used **import fraction**, expression

**Fraction\(1,2\)** would have changed to **fraction.Fraction\(1,2\)**

Here is the module \(file\) **mymath.py** that contains the **gcd** \(greatest common divisor\) function.

![](https://lh4.googleusercontent.com/ZN1KNlfXo5ZiWoKg_q6x-uIwteL9pxMfVynqDezgtvm9Z0WrmLYdftrIdZH5Z6xf7bZjlMLEDymFfD2V6ujw-5fhZi6ykOibMMy6F1Aom32HQcY0j0gFd7_VbWiadXaRyhUhy6OA)

Notice how it is used in the **Fraction** class

```
n = mymath.gcd(self.a, self.b)
```

because the module was imported with

```
import mymath
```

## Objects in Python Assignment:\(A - 8 marks\)

**Task 1:**  Add two methods to the Fraction class called **plus\(self, f\)** and **minus\(self, f\)** that will add or subtract two fractions. (2 marks)

**Task 2:**  Demonstrate how to use the two methods above in **main.py**. (1 mark)

**Task 3:** Create a new class called **Student** in a file named **student.py** \(see below\). (1 mark)

![](https://lh5.googleusercontent.com/ucDesuFZY9FtMTbRzKALneF1eR9nB7MGLgTZxnpC4C77R1r2JYdpTpGX3Fq68pjIkZedLuzskFhAYR2hhWVeEbs8rx4asi1dx6wacDafnjXrbZvCtiuFsdtlMER6sNNw6fZ7qdks)

**Task 4:** Create a **main.py** file that creates five Students, such as… (2 marks)

```
s1 = Student(“Armstrong”,“Christian”,“12”,“Bishop”,“Woloshyn”)
s2 = Student(“Chen”,“Leo”,“12”,“Graham”,“PGuse”)
s3 = Student(“Ding”,“Jack”,“12”,“Baker”,“PGuse”)
s4 = Student(“Gu”,“Juliet”,“12”,“Graham”,“Stacey”)
s5 = Student(“Hu”,“Amber”,“12”,“Graham”,“AGuse”)
s6 = Student(“Jansz-Tatem”,“Eli”,“12”,“Baker”,“Holland-McLeod”)
```

**Task 5:**  In the **main.py** file create a list of the students. For example, (1 mark)

```
student_body = [s1, s2, s3, … ]
```

**Task 6:** Save your list of students, called **student\_body** to a file named **student\_body.csv**. Your file should look like the following (1 mark)

_\(Notice the commas between each item\)_.

```
Armstrong, Christian, 12, Bishop, Woloshyn
Chen, Leo, 12, Graham, PGuse
...
```

**Note:** You’ll need to create a **string** out of each set of Student data before writing it to the file.  The format of the **string** is determined by the **\_\_str\_\_** function in the Fraction class.

If your output file is assigned the variable **myFile**, then to add all the students in the list to the file use the following group of statements

```
myFile = open("student_body.csv",'w')
for s in student_body:
    myFile.write( str(s) )
myFile.close()

```
