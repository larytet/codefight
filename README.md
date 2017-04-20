# codefight

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
