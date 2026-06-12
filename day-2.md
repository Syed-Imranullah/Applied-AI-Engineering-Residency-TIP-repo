# Day 2

Problem: 
leetcode link: https://leetcode.com/problems/best-time-to-buy-and-sell-stock/description/

```js
//js solution
function maxProfit(prices) {
  let minPrice = Infinity;
  let maxProfit = 0;
  for (let i = 0; i < prices.length; i++) {
    if (prices[i] < minPrice) {
      minPrice = prices[i];
    } else if (prices[i] - minPrice > maxProfit) {
      maxProfit = prices[i] - minPrice;
    }
  }
  return maxProfit;
}
```
Input: prices = [7,1,5,3,6,4]
Output: 5

Algorithm: set the minPice to infinity, and maxProfit of zero. then loop through the prices and check if the current price is less than minPrice, then update minPrice to the value otherwise calculate the profit by subtracting minPrice from the current price if that profit is greater than maxProfit update maxProfit then return maxProfit after the loop

Python Solution:

```py
# solution here
class Solution(object):
    def maxProfit(self, prices):
        """
        :type prices: List[int]
        :rtype: int
        """
        min_price = float('inf')
        max_profit = 0

        for price in prices:
            if price < min_price:
                min_price = price
            elif price - min_price > max_profit:
                max_profit = price - min_price

        return max_profit

```
