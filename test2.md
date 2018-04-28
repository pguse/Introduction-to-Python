# Working with Files

### Reading a Text File:

To open and read a text file in Python, you run the following lines_ \(assuming the file  **myInfo.txt** is in the same folder as your Python program\)._

```
inputFile = open('myInfo.txt', 'r')

info = inputFile.read()

print(info)
```

This program will print the entire contents of the file to your screen/console.  Notice that the file extension of the text file must be included in the file name.  Also, the argument 'r' in the open\(\) function indicates that we are only reading the information from the file, not modifying its contents.

If you want to read in the information of a file** line-by-line**, the following code is used using a another form of a Python loop:

```
for line in inputFile:
    print(line)
```

### Writing a Text File

To write information to a new text file in Python, you run the following lines of Python code.

```
outputFile = open('output.txt', 'w')
outputFile.write("I have written this text to a new file named output.txt")
outputFile.write("\nI have written a second line of information to output.txt")
```

If you look in the folder containing your Python file, you should find a new file named output.txt.  **Notice **the use of the character '\n'.  This indicates that we want the string to be written to a new line in the file.

When you are finished working with files in Python, it is important to 'close' them using the following commands

```
inputFile.close()
outputFile.close()
```



