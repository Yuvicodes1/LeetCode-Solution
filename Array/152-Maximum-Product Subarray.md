![image](https://github.com/user-attachments/assets/9e4542e6-a777-4f62-8749-29e336af9ba7)

LINK : https://leetcode.com/problems/maximum-product-subarray/description/

## SOLUTION CPP

```cpp
class Solution {
public:
    int maxProduct(vector<int>& nums) {
        int n = nums.size();
        int maxProd = nums[0];
        int maxSoFar = nums[0], minSoFar = nums[0];

        for (int i = 1; i < n; i++) {
            if (nums[i] < 0) swap(maxSoFar, minSoFar);
            maxSoFar = max(nums[i], nums[i] * maxSoFar);
            minSoFar = min(nums[i], nums[i] * minSoFar);
            maxProd = max(maxProd, maxSoFar);
        }

        return maxProd;
    }
};
```
![image](https://github.com/user-attachments/assets/f928254b-0d01-496d-911c-b4190eede1a2)
