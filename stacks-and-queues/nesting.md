# Nesting
```python
def solution(S):
    # Implement your solution here
    brackets = { "(" : ")" }
    to_match = ["("]
    stack = []

    for s in S:
        if s in to_match:
            stack.append(s)
        else:
            if len(stack) == 0:
                return 0

            if s != brackets[stack.pop()]:
                return 0

    return 1 if len(stack) == 0 else 0
```
### Brief Explanation on Solution
If opening bracket, add to stack. 

If closing bracket, check if anything to pop from stack. If no, return 0. If yes, check if closing corresponds to opening bracket. 

Return 1 only if the length of the stack is 0 and return 0 otherwise. 

### Time Analysis
O(N)

