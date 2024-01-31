# Max Slice Sum
```python
def solution(A):
    # Implement your solution here
    max_sum_here = float('-inf')
    max_sum_overall = float('-inf')

    for a in A:
        max_sum_here = max(max_sum_here + a, a) # discard the previous slice as it is less than curr val
        max_sum_overall = max(max_sum_overall, max_sum_here)

    return max_sum_overall
```
### Brief Explanation on Solution
Maintain two variables:
1. For the max sum at a specific index 
2. For the overall max sum 

Iterate each variable in the list,
- Find the max sum of the previous slice + current value vs. current value -> If the current value is > previous slice + current value, no point keeping that slice. Replace the max value. 
- Find the max sum overall, by comparing the max sum overall with the max sum at the current index. 

Return the max sum obtained. 

### Time Analysis
O(N)





