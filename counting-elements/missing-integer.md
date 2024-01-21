# Missing Integer
```python
def solution(A):
    # Implement your solution here
    setA = set(A)

    for i in range(1, 1000001):
        if i not in setA:
            return i
```
### Brief Explanation on Solution
Reduce A to only unique values. 

For loop the array between all the possible positive integers, for each value, check if it exists in the unique set. If it does not, it will be the smallest missing positive integer. 

### Time Analysis
O(N) or O(N * log(N))