# Triangle
```python
def solution(A):
    # Implement your solution here
    A.sort()

    for idx in range(0, len(A) - 2):
        P = A[idx]
        Q = A[idx + 1]
        R = A[idx + 2]
        if (P + Q > R) and (Q + R > P) and (R + P > Q):
            return 1
    
    return 0
```
### Brief Explanation on Solution
Sort the array. 

Iterate until the third last index and compare each set of 3 with the criteria. If met, return True. 

Else, return False.

### Time Analysis
O(N * log(N))

