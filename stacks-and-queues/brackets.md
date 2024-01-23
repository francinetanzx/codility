# Brackets
```python
def solution(S):
    # Implement your solution here
    if len(S) % 2 == 1:   return 0
    matched = {"]":"[", "}":"{", ")": "("}
    to_push = ["[", "{", "("]
    stack = []
    for element in S:
        if element in to_push:
            stack.append(element)
        else:
            if len(stack) == 0:
                return 0
            elif matched[element] != stack.pop():
                return 0
    if len(stack) == 0:
        return 1
    else:
        return 0
```
### Brief Explanation on Solution
If the length of the string is not even, return 0. 

For each open bracket encountered, push it into the stack. Whenever a closing bracket is found, first check if the stack has values to pop. If no, return 0. Next, check if the value popped matches the respective opening bracket. If no, return 0. 

If the length of the final stack is 0, meaning no leftover brackets, return 1. Else, return 0. 

### Time Analysis
O(N)

