# MaxCounters
```python
def solution(N, A):
    # Implement your solution here
    
    max_counter = 0
    counters = [0] * N

    for a in A:
        if a >= 1 and a <= N:
            counters[a-1] += 1
            if counters[a-1] > max_counter:
                max_counter = counters[a-1]
        
        if a == (N + 1):
            counters = [max_counter] * N

            if counters[0] > max_counter:
                max_counter = counters[0]
    
    return counters
```

### Brief Explanation on Solution
Maintain a counter to keep track of the largest counter within the array. 

Construct a N-sized array of zeros. 

For each value within A, if the value >= 1 and <= N, increment the value at index (a - 1). After the increment, if the counter is > max_counter, replace the max_counter. If the value is equals to N + 1, reconstruct the array with the max_counter. Check again if after the reconstruction, if the value at the first index is > max_counter, replace if so. 

*Note: Total Score obtained was 77%, 100% on Correctness and 60% on Performance. 

### Time Analysis
N/A
