# Working with Objects

## Introduction

Python works with numbers essentially just like a calculator. When you type:

```
> 1 / 2
0.5
```

it automatically produces a decimal \(float-point\) value. By creating the Fractionclass, we are going to enable Python to deal with fractions just like we might in an introductory math class. Aclassacts like atemplateorblueprintthat includes two features:

1. Data- often called fields

2. Methods- what we have so far called functions

The file below \(fraction.py\) shows an example of a Fraction class. It involvesdata\(the fields\) that represents thenumerator\(self.a\) anddenominator\(self.b\) of a Fraction. These values are initialized when the Fraction is created - the special Python function\_\_init\_\_\(self, \_a, \_b\), called theconstructor, assigns/binds the input values \_a and \_b to the field identifiers/variables \(self.a and self.b\).

![](https://lh3.googleusercontent.com/g2JJQA8XvfZKJCYG35WrWIQ0tzWO4F5m18CODRL5PXnR1BNFn5FX53lA-iGOQI-6meiAitheED5IqyxjmuhokrVq9XkEziGO-UFTjox1t_F2YwHmgPaXSTxV2hfSI1wtxGrUXRLS)

The other special Python function in this class is

```
__str__(self)
```

. It returns the string that represents a particular Fraction when you attempt to print it out.

The unusual part about classes in Python is the wordself. In this example, the Fraction class represents any fraction. The wordselfrefers to the particular fraction you have created with this class. It must be used as the first argument in the definition of everymethodand in the names of each field. Note:The wordselfnever occurs when you actually call amethod.

Here is how to use the class:

![](https://lh3.googleusercontent.com/Bqy13Vb24ajiz8cgKBFO7Gv0mzr6RDlqeUp4jdKtJKLFhgxNcb1bpqjNIwumJYfou2_WTe1sjKNo1vQC0mi-WgbgcHQ1c_QRPrh7lRR1hvndnZnbibiAk10HMBNHjg0YYqXFjX47)

Notice how a Fraction is created, using the word Fraction \(the name of the class\).

```
f1 = Fraction(1,2)
```

The values input to this method match those in the\_\_init\_\_function, because this is the method run when a Fraction is created. This is called creating aninstanceof the Fraction class or in other wordsf1, f2,andf3are calledobjectsof type Fraction.

Notice how theproductof two Fractions is calculated.

```
f3 = f1.prod(f2)
```

The dot operatoris used to call a method \(eg.prod\) on an object \(eg.f1\) of a class. The definition of theprodmethod is,

```
def prod(self, f):
    return Fraction(self.a * f.a , self.b * f.b)
```

It returns a Fraction with a new numerator \(self.a \* f.a\) and denominator \(self.b \* f.b\). The valueself.ais the numerator of the calling Fraction \(eg.f1in the example above\), whilef.ais the numerator of the Fraction input to theprodfunction \(eg.f2in the example above\).

Notice how you could apply two methods to a single Fraction object.

```
f1.prod(f2).simplify()
```

The expression

```
f1.prod(f2)
```

produces a new Fraction object that the method simplify\(\) is then applied to.

## Using external files:

All the files in this example:main.py,mymath.py, andfraction.pymust be contained in thesamefolder. In order to use the Fraction class inmain.py, the line

```
from fraction import *
```

is necessary. If we had instead usedimportfraction, expression

Fraction\(1,2\) would have changed to fraction.Fraction\(1,2\)

Here is the module \(file\) mymath.py that contains the gcd \(greatest common divisor\) function.

![](https://lh4.googleusercontent.com/ZN1KNlfXo5ZiWoKg_q6x-uIwteL9pxMfVynqDezgtvm9Z0WrmLYdftrIdZH5Z6xf7bZjlMLEDymFfD2V6ujw-5fhZi6ykOibMMy6F1Aom32HQcY0j0gFd7_VbWiadXaRyhUhy6OA)

Notice how it is used in the Fraction class

```
n = mymath.gcd(self.a, self.b)
```

because the module was imported with

```
import mymath
```

## Objects in Python Assignment:\(A - 6 marks\)

1. Add two methods to the Fraction class called **plus\(self, f\)** and **minus\(self, f\)** that will add or subtract two fractions. Demonstrate how to use them in **main.py**.

2. Create a new class called **Student** in a file named **student.py** \(see below\).

![](https://lh5.googleusercontent.com/ucDesuFZY9FtMTbRzKALneF1eR9nB7MGLgTZxnpC4C77R1r2JYdpTpGX3Fq68pjIkZedLuzskFhAYR2hhWVeEbs8rx4asi1dx6wacDafnjXrbZvCtiuFsdtlMER6sNNw6fZ7qdks)

    3.  Create a **main.py** file that creates five Students, such as…

```
s1 = Student(“Jones”,“Brittany”,“10”,“Graham”,“Acton”)
s2 = Student(“Hodges”,“Alex”,“12”,“Bishop”,“Stacey”)
s3 = Student(...
```

    4.  Create a list of the students. For example,

```
student_body = [s1, s2, s3, … ]
```

**Challenge:**  Save your list of students, called **student\_body** to a file named **student\_body.txt**. Your file should look like the     following \(Notice the commas between each item\).

| Jones, Brittany, 10, Graham, ActonHodges, Alex, 12, Bishop, Stacey |
| :--- |


**Hint:** You’ll need to create a String out of each set of Student data before writing it to the file.

