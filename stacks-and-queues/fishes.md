# Brackets
```python
def solution(A, B):
    # Implement your solution here
    l = 0
    fishes = []

    for idx in range(len(B)):
        if B[idx] == 1:
            fishes.append(A[idx])
        else:
            while len(fishes) > 0:
                if fishes[-1] < A[idx]:
                    fishes.pop()
                else:
                    break
            else:
                l += 1

    l += len(fishes)
    return l
```
### Brief Explanation on Solution
For each fish in B, check if the direction is upstream or downstream. 

If downstream, append the size to downstream-only array.

If upstream, check if the there are downstream fishes to compare sizes with. If no, add one to the upstream fish count. If yes, sieve through the past fishes in the fish stack and if the size of previous fish is less than the current fish, pop. Else, break. 

Add the length of the downstream-only array and the upstream counter to get the fishes left. 

### Time Analysis
O(N)



