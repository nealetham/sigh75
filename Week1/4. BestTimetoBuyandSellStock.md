# Best Time to Buy and Sell Stock

## Initial Solution

Intuitively, we want to find the max price for all future days. We will subtract the today's price from the max price to calculate profit. We simultaneously maintain a variable to keep track of the maximum profit obtained thus far.

Time Complexity: O(n^2)
Space Complexity: O(1)

```python
def maxProfit(self, prices):
    curr_max = 0
    for i in range(0, len(prices) - 1):
        profit = max(prices[i+1:]) - prices[i]
        if profit > curr_max:
            curr_max = profit

    return curr_max
```

However, this solution exceeds the time limit. Considering that, we need to modify the solution such that it is only a one-pass.

## Improved Solution

Here, with this one pass solution, instead of looking forward into the future (which is rather intuitive), we look backwards to find the global minimum of prices observed. As such, we maintain an invariant that at iteration i, curr_min < prices[0...i].

Time Complexity: O(n)
Space Complexity: O(1)


```python
def maxProfit(self, prices):
    curr_min = float('inf')
    max_profit = 0
    for price in prices:
        if price < curr_min:
            curr_min = price
            continue
        
        if price > curr_min:
            new_profit = price - curr_min
            max_profit = max(new_profit, max_profit)
            continue
    
    return max_profit
```

Completed: 6/10/2023