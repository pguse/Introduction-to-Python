# Input/Ouput - Keyboard

## The input\(\) Function

The **input\(\)** function is used as follows to get text input from the keyboard.

```
name = input("Enter your name: ")
```

The string **"Enter your name: "** is displayed and then the program waits for you to type something and press the **Enter/Return** key.  The variable **name **stores the characters you have typed and is of type **string**.  Here is an example of how the code might run.

```
>> name = input("Enter your name:")
Enter your name: Mr. Guse
>> type(name)
=> <class 'str'>
```

It doesn't matter whether you type letters & punctuation or numbers, the variable will still be of type string. For example,

```
>> year = input("Enter the year:")
Enter the year: 2017
>> type(year)
=> <class 'str'>
```

This is important to realize if you intend on doing some sort of mathematical calculation with an input value.  For example, when you multiply the year by two in the following code

```
>> year = input("Enter the year:")
Enter the year: 2017
>> year*2
=> '20172017'
```

the result is the repetition of a string instead of doubling the value 2017.  To remedy this, we can use the **int\(\)** function as follows to change the input value to an integer.

```
>> year = int( input("Enter the year:") )
Enter the year: 2017
>> year*2
=> 4034
```

Similarly, if we wanted a decimal value we could use the **float\(\)** function as follows:

```
>> balance = float( input("Enter your bank balance:") )
Enter your bank balance:  576.10
>> balance*2
1152.2
```

## The print\(\) Function

The **print\(\)** function is used as follows to output text to the screen.

```
>> print("Hello World!")
Hello World
```

It will output the **value **of any variable, where the **comma **is used to insert a **space \(by default\)** between values.  For example,

```
>> course = "ICS3U"
>> print("Welcome to our", course, "course!")
Welcome to our ICS3U course!
```

or

```
>> year = 2017
>> print("The year is", year)
The year is 2017
```

If you want to change what the comma inserts, you can use set the **sep **parameter as follows:

```
>> hour = 2
>> minutes = 11
>> print(hour,minutes,sep=":")
2:11
```

By default, the print statement goes to a new line after it executes.  If you wish to print on the same line with multiple print statements \(as in a loop - see later section\), you can set the **end **parameter.  The following code prints on separate lines, as shown below:

```
>> for i in range(3): 
..   print("Hello") 
..   
Hello
Hello
Hello
```

whereas this code prints on the same line.

```
>> for i in range(3): 
..   print("Hello", end=" ") 
..   
Hello Hello Hello   
```



