## 121. Best Time to Buy and Sell Stock

```java
class Solution {
    public int maxProfit(int[] prices) {
        int maxProfit=0;
        int cost=prices[0];
        for(int i:prices)
        {
            int profit=i-cost;
            maxProfit=Math.max(profit,maxProfit);
            cost=Math.min(cost,i);
        }return maxProfit;
    }
}
