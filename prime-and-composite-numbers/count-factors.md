# Count Factors
```python
def solution(N):
    # Implement your solution here

    result = 0
    i = 1

    while ((i * i) < N):
        if N % i == 0:
            result += 2
        i += 1
    
    if i * i == N:
        result += 1
    
    return result
```
### Brief Explanation on Solution
One of the factors will always be less than the sqaureroot of N, while the other is more than (except for values like 25, where 5 is the squareroot of N).

Bearing that in mind, we traverse squareroot of N values to find which ones, N can be divided with. Every value that we find, we increment results by 2. To account for the one below the squareroot of N and the one above the squareroot of N. 

Finally, check again for edge cases like 25. The i coming out of N should either be the closest integer value to the sqaureroot or the actual value. 

### Time Analysis
O(sqrt(N))



