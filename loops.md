# Loops - Repetition in Python

## The for-loop:

This type of loop is useful when you know how many times to repeat your instructions. For example.

```
for i in range(3):
    print “Hello everyone!”
print “Loop finished.”
```

produces the output:

```
Hello everyone!
Hello everyone!
Hello everyone!
Loop finished
```

The function **range**\(3\) causes the loop to repeat 3 times. Changing it to **range**\(5\) would repeat the loop 5 times. The variable** i **takes on the values 0, 1, and 2 during each repetition of the loop. For example,

```
for i in range(3):
    print str(i) +“. Hello everyone!”
```

produces the output:

```
0. Hello everyone!
1. Hello everyone!
2. Hello everyone!
```

The variable **i** can be used as a type of counter in the following way:

```
count = 0
for i in range(3):
    count = count + i
    print count, i
```

produces the output:

```
0 0
1 1
3 2
```

The **range**\(3\) function can be modified in the following ways:

```
for i in range(1,4):
    print str(i) +“. Hello everyone!”
```

produces the output:

```
1. Hello everyone!
2. Hello everyone!
3. Hello everyone!
```

Notice how the variable** i **now starts at a value of 1 but only goes up to the maximum value \(in this case 4\) but does not take on a value of 4. Also,

```
for i in range(1,7,2):
    print str(i) +“. Hello everyone!”
```

produces the output:

```
1. Hello everyone!
3. Hello everyone!
5. Hello everyone!
```

In this case, the variable** i** takes on values in steps of 2. We can also count backwards by doing the following:

```
for i in range(4,1,-1):
    print str(i) +“. Hello everyone!”
```

produces the output:

```
4. Hello everyone!
3. Hello everyone!
2. Hello everyone!
```

Again, the variable** i **does not take on the minimum value of 1, but only goes down to it.

## The for-loop - without the range\(\) function:

The **for-loop** can be used without the **range**\(\) function in a couple ways. It can be used to pass through the characters in a string as follows:

```
name =“Ada”
for ch in name:
    print( ch )
```

produces the output:

```
A
d
a
```

It can also be used to pass through the items in a **list **as follows:

```
names = [“Ada”, “Python”, “Pyret”]
for language in names:
    print language
```

produces the output:

```
Ada
Python
Pyret
```



