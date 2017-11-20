# Algorithms - Sorting

Given a list of numbers called **myList**:

| 0 | 1 | 2 | 3 | 4 | 5 | 6 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| 76 | 10 | 5 | -17 | 34 | 25 | 2 |

  
If we wanted to sort the list, what steps/**algorithm** could we use to arrange the numbers in order from least to greatest? One method is called the **selection sort**.

### The selection sort \(algorithm\)

The selection sort involves scanning the list from the beginning to find the position of the **minimum **value, then placing the minimum value at the beginning of the list, by **swapping **the two values. This is **repeated **now starting at the next position in the list. Find the **minimum **value in the remainder of the list and swap the two values. Repeat until you have passed through the entire list.

After the first pass through the list the **minimum **value found will be **-17**. The Python code to find the **index **of the **minimum **value in the list is

```
myList = [76,10,5,-17,34,25,2]

index = 0
for i in range( 1, len(myList) ):
	if myList[i] < myList[index]:
    	index = i
print( myList[index] )
```

The print statement is used to check whether we have found the correct minimum value.

| 0 | 1 | 2 | 3 | 4 | 5 | 6 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| **76** | 10 | 5 | **-17** | 34 | 25 | 2 |

The values in** position 0 and position 3** will now be swapped. The Python code to swap the two values is

```
swap = myList[0]
myList[0] = myList[index]
myList[index] = swap

print( myList )
```

**Notice **that myList\[0\] must first be saved using another variable so that its value is not_** 'lost'**_** **during the assignment statement in line 2.  The new list looks like this,

| 0 | 1 | 2 | 3 | 4 | 5 | 6 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| **-17** | 10 | 5 | **76** | 34 | 25 | 2 |

To sort the remainder of the list, the same algorithm is followed **starting at index 1**, so for the next pass the Python code would be,

```
index = 1
for i in range( 2, len(myList) ):
	if myList[i] < myList[index]:
    	index = i
print( myList[index] )

swap = myList[1]
myList[1] = myList[index]
myList[index] = swap

print( myList )
```

The new list looks like this after the second pass through,

| 0 | 1 | 2 | 3 | 4 | 5 | 6 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| -17 | **2** | 5 | 76 | 34 | 25 | **10** |

We continue to **repeat **these pieces of code from index 2 to 5, the second last index of the list.  If you look at the pattern of the index values in the code above, it should be evident that we could simply use a second loop as follows,

```
for j in range(0, len(myList) ):
	index = j
	for i in range( j+1, len(myList) ):
    	  if myList[i] < myList[index]:
          	index = i

	swap = myList[j]
	myList[j] = myList[index]
	myList[index] = swap

	print( myList )
```

The** print\( myList \) **statement simply shows the list after each pass through.  It can be removed once you are convinced that the code works

