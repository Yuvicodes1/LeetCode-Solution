## 121. Best Time to Buy and Sell Stock
https://leetcode.com/problems/best-time-to-buy-and-sell-stock/description/

## Solutions
**TLE**
```cpp
class Solution {
public:
    int maxProfit(vector<int>& prices) {
        int maxP=0;
        int n=prices.size();
        for(int i=0;i<n;i++){
            for(int j=i+1;j<n;j++){
                if(maxP<(prices[j]-prices[i]))
                    maxP=prices[j]-prices[i];
            }
        }
        return maxP;
    }
};
```

**ACCEPTED SOLUTION**
```cpp
class Solution {
public:
    int maxProfit(vector<int>& prices) {
        int maxProfit = 0;
        int minPrice = INT_MAX;

        for (int i = 0; i < prices.size(); i++) {
            minPrice = min(minPrice, prices[i]);
            maxProfit = max(maxProfit, prices[i] - minPrice);
        }

        return maxProfit;
    }
};
```
![image](https://github.com/user-attachments/assets/7314682c-0a90-48b7-be3f-af505d97ba1c)
