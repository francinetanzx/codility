# Distinct
```python
def solution(N):
    # Implement your solution here
    
    min_perimeter = float('inf')
    A = 1

    while (A * A) < N:
        if N % A == 0: 
            B = N / A
            min_perimeter = min(min_perimeter, 2 * (A + B))
        A += 1
    
    if A * A == N:
        min_perimeter = min(min_perimeter, 2 * (A + A))
    
    return int(min_perimeter)
    
```
### Brief Explanation on Solution
Adapted from count factors solution, to instead of counting factors, use the factors to count the perimeter. 

The only catch here is that min_perimeter has to be set as an infinitely large number by using ```float('inf')``` and right before returning, convert it back to an integer. 

### Time Analysis
O(sqrt(N))

