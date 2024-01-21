# FrogRiverOne
```python
def solution(X, A):
    # Implement your solution here
    when_to_cross = -1

    flags = [False] * X
    flag_counter = 0

    for idx in range(0, len(A)):

        if A[idx] <= X and flags[A[idx] - 1] == False:
            flags[A[idx] - 1] = True
            flag_counter += 1
        
        if flag_counter == X:
            when_to_cross = idx
            break
    
    return when_to_cross
```

### Brief Explanation on Solution
Initialise a return value of -1.

Maintain an array of flags, each defaulted to false. The index represents the numbers that need to appear for the frog to cross. 

Maintain a counter that increments each time the flag in the flags array changes from false to true. 

Iterate across all the values within the array
- If the value is less than or equals to the length of the flags array (within bounds), check if the flag has already been set to True. If no, change it and increment the flag counter by 1
- Check if the flag counter equals to X. If yes, it means the frog can now cross and replace the return value with the current index. 

Finally, compare the sum of the occurences with the length. If the same, it means that every value for the array to be considered a permutation exists. 

### Time Analysis
O(N)