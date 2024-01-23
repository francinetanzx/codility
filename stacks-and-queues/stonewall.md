# Stone Wall
```python
def solution(H):
    # Implement your solution here

    # [8, 8, 5, 7, 9, 8, 7, 4, 8]

    blocks_needed = 0
    working_space = []
    
    for idx in range(0, len(H)):
        if len(working_space) == 0:
            working_space.append(H[idx])
            blocks_needed += 1
        # account for same length = same block
        elif working_space[-1] == H[idx]:
            working_space.append(H[idx])
        # account for blocks needed when height increases
        elif working_space[-1] < H[idx]:
            working_space.append(H[idx])
            blocks_needed += 1
        # account for blocks needed when height decreases - searches if there is a past height to use
        elif working_space[-1] > H[idx]:
            same_block = False
            for lidx in range(idx - 1, -1, -1):
                if H[lidx] < H[idx]: break
                elif H[lidx] == H[idx]: same_block = True
            
            working_space.append(H[idx])
            
            if not same_block: blocks_needed += 1
    
    return blocks_needed
```
### Brief Explanation on Solution
Refer to comments for explanation

### Time Analysis
O(N**2)

*Note: Total Score obtained was 71%, 100% on Correctness and 55% on Performance. 


