# Nesting
```python
def solution(A):
    # Implement your solution here
    threshold = len(A) // 2

    occurrences = dict()

    for idx, val in enumerate(A):
        occurrences[val] = occurrences.get(val, 0) + 1

        if occurrences[val] > threshold:
            return idx
    
    return -1
```
### Brief Explanation on Solution
Find the threshold. 

Maintain a dictionary of occurrences. 

For each value, update the value within the dictionary. After the update, check if it is above the threshold. If so, immediately return the index. 

Else, return -1. 

### Time Analysis
O(N*log(N)) or O(N)




    