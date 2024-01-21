# PermCheck
```python
def solution(A):
    # Implement your solution here
    occurrences = [0] * len(A)

    for idx in range(0, len(A)):
        if A[idx] <= len(A) and occurrences[A[idx] - 1] == 0:
            occurrences[A[idx] - 1] = 1
    
    return int(sum(occurrences) == len(occurrences))
```
### Brief Explanation on Solution
Maintain an array of zeros, their indexes representing each of the value that has to exists in order for the array to be considered a permutation. An array of occurrences.

Iterate across all the values within the array
- If the value is less than or equals to the length of the array (within bounds), check if this occurrence has already been taken note of in the array of occurrences (zero changes to a one)

Finally, compare the sum of the occurences with the length. If the same, it means that every value for the array to be considered a permutation exists. 

### Time Analysis
O(N) or O(N * log(N))

