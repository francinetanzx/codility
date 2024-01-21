# Max Product Of Three
```python
def solution(A):
    # Implement your solution here

    A.sort()

    max1 = A[len(A) - 1] * A[len(A) - 2] * A[len(A) - 3]
    max2 = A[0] * A[1] * A[len(A) - 1]

    return max(max1, max2)
```
### Brief Explanation on Solution
Sort the array. 

Maximums
- Max 3 Positives 
- Min 2 Negatives (to get Positive) * Max Positive 

Compare the two possible maximums to get the best value. 

### Time Analysis
O(N * log(N))

