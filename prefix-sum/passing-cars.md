# Passing Cars
```python
def solution(A):
    # Implement your solution here
    zeros_thus_far = 0
    pairs = 0

    for a in A:
        if a == 0:
            zeros_thus_far += 1
        else: 
            pairs += zeros_thus_far

    if pairs > 1000000000: return -1

    return pairs
```
### Brief Explanation on Solution
Maintain two variables:
1. One for the zeros encoutered thus far 
2. One for all the possible 1-0 pairs such that 0 < 1

Iterate through the list of items, 
- Whenever a zero is encountered, increment the first variable
- Whenever a one is encountered, add the current value in the first variable to the second variable (that is the possible pairs that can form)

Check for if pairs > 1000000000 to return -1

### Time Analysis
O(N)