# Max Profit
```python
def solution(A):
    # Implement your solution here

    lowest_price = 200001
    most_profit = 0

    for todays_price in A:
        lowest_price = min(lowest_price, todays_price)
        most_profit = max(todays_price - lowest_price, most_profit)
    
    return most_profit
```
### Brief Explanation on Solution
Maintain two variables:
1. Lowest price of the list (*Note: Important to set this as the highest value possible, in this case 200001)
2. Most profit between two prices on the list 

Iterate through the list, for each value: 
- Check if it is the lower than the lowest price. If so, replace. 
- Check if by deducting today's price and the lowest price, do we get the most profit. If so, replace. 

Return the most profit obtained. 

### Time Analysis
O(N)


