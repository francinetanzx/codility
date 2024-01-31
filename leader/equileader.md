# Nesting
```python
def solution(A):
    # Implement your solution here

    # handle length = 0
    if (len(A)) == 1:
        return 0

    # find the leader and leader count
    threshold = len(A) // 2
    count = dict()
    leader = None

    for idx, val in enumerate(A):
        count[val] = count.get(val, 0) + 1

        if count[val] > threshold:
            leader = val
    
    # handle if there is no leader
    if leader == None:
        return 0

    # initialize all the vars needed
    first_half_counter = 0
    second_half_counter = count[leader]
    equileader_counter = 0

    # traverse again to find the index counts for equileaders 
    for idx in range(len(A) - 1):
        if A[idx] == leader: 
            first_half_counter += 1
            second_half_counter -= 1

        first_half = (first_half_counter/(idx + 1)) > 0.5
        second_half = (second_half_counter/(len(A) - idx - 1)) > 0.5

        if first_half and second_half:
            equileader_counter += 1
    
    return equileader_counter
```
### Brief Explanation on Solution
Handle if list has only one value, finding equileaders is not possible. 

Find the leader amongst the list as well as the count of the leader within the list. 

Handle a scenario when there is no leader. 

Maintain a counter for both halves - first half will be 0 and second half will be the count of the leader. 

Go through the entire list (until N-1), check if the current value is equals to the leader. If so, add to the counter of the first half and remove from the second half. 

Check if the leader value make up the majority (>0.5) of the first half and second half using the counters and the expected value in each half. 
- If yes, increment the equileader counter

### Time Analysis
O(N)




    