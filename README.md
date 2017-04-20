# codefight

For the sake of desperate Google searchers here are Python solutions

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
