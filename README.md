# codefight

For the sake of desperate Google searchers here are Python solutions

```Python
def add(param1, param2):
    return param1+param2

# Given a year, return the century it is in. The first century spans from the year 1 up to and including the year 100, the second - from the year 101 up to and including the year 200, etc.
def centuryFromYear(year):
    if year % 100 != 0: return year / 100 + 1
    else: return year /100 

# Given the string, check if it is a palindrome.
def checkPalindrome(inputString):
    return inputString == inputString[::-1]
```



Given an array of integers, find the pair of adjacent elements that has the largest product and return that product.

```Python
def adjacentElementsProduct(inputArray):
    max_product = inputArray[0] * inputArray[1]
    array_len = len(inputArray)
    for idx in range(0, array_len-1):
        product = inputArray[idx] * inputArray[idx+1]
        max_product = max(max_product, product)
    return max_product
```

Below we will define an n-interesting polygon. Your task is to find the area of a polygon for a given n.

A 1-interesting polygon is just a square with a side of length 1. An n-interesting polygon is obtained by taking the n - 1-interesting polygon and appending 1-interesting polygons to its rim, side by side. You can see the 1-, 2-, 3- and 4-interesting polygons in the picture below.

```Python
import math
def shapeArea(n):
    return (2*n-1)+2*(n-1)*(n-1)
#n+(n-1)*(2*n-1)
#math.pow(((n*2)-1), 2) - (((n * (n-1)) / 2) * 4)
```


```Python
Ratiorg got statues of different sizes as a present from CodeMaster for his birthday, each statue having an non-negative integer size. Since he likes to make things perfect, he wants to arrange them from smallest to largest so that each statue will be bigger than the previous one exactly by 1. He may need some additional statues to be able to accomplish that. Help him figure out the minimum number of additional statues needed.
```

def makeArrayConsecutive2(statues):
    statues.sort()
    array_size = len(statues)
    max_val = statues[-1]
    min_val = statues[0]
    return (max_val - min_val) - (array_size - 1) 



Given a sequence of integers as an array, determine whether it is possible to obtain a strictly increasing sequence by removing no more than one element from the array.

```Python
def almostIncreasingSequenceS(sequence, pos, skipped):
    i = j = 0
    while True:
        i = j
        j = j + 1
        if i == skipped:
            i = i+1
            j = i+1
        elif j == skipped:
            j = j + 1
            
        if j >= len(sequence):
            return True
        if i >= len(sequence):
            return True
        
        if (sequence[i] >= sequence[j]):
            return False
        

def almostIncreasingSequence(sequence):
    i = 0
    while True:
        if (sequence[i] >= sequence[i+1]):
            res = almostIncreasingSequenceS(sequence, i, i)
            res = res or almostIncreasingSequenceS(sequence, i, i+1)
            if not res:
                return False
            
        i = i + 1
        if i >= (len(sequence)-1):
            return True
```


After becoming famous, CodeBots decided to move to a new building and live together. The building is represented by a rectangular matrix of rooms, each cell containing an integer - the price of the room. Some rooms are free (their cost is 0), but that's probably because they are haunted, so all the bots are afraid of them. That is why any room that is free or is located anywhere below a free room in the same column is not considered suitable for the bots.

Help the bots calculate the total price of all the rooms that are suitable for them.
```Python
# Brute force
def matrixElementsSum(matrix):
        forbidden = {}
        cost = 0
        for line in xrange(0, len(matrix)):
                for column in xrange(0, len(matrix[0])):
                        val = (matrix[line])[column]
                        if val == 0:
                                for i in xrange(line, len(matrix)):
                                        forbidden[(i, column)] = True
                        if not (line, column) in forbidden:
                                cost = cost + val
                        else:
                                print "skip",line, column
        print forbidden
        return cost

# Break out of inner loop by lines if I hit zero element
def matrixElementsSum(matrix):
        cost = 0
        for column in xrange(0, len(matrix[0])):
                for line in xrange(0, len(matrix)):
                        val = (matrix[line])[column]
                        if val != 0:
                                cost += val
                        else:
                                  break
        return cost
                        

```


Given an array of strings, return another array containing all of its longest strings.
```Python
def allLongestStrings(inputArray):
    max_len = 0
    for s in inputArray:
        max_len = max(max_len, len(s))
    
    res = []
    for s in inputArray:
        if len(s) == max_len:
            res.append(s)
            
    return res
```
