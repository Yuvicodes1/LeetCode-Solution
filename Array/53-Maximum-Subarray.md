## 53. Maximum Subarray
LINK : https://leetcode.com/problems/maximum-subarray/description/
 **Given an integer array nums, find the subarray with the largest sum, and return its sum.**

Solution 1 : BRUTE FORCE : TLE
Solution 2: KADANE'S Algo (CPP):
```cpp
class Solution {
public:
    int maxSubArray(vector<int>& nums) {
        //or a dp approach? maximum sum ending at that particular index?
        int n = nums.size();
        vector<int> dp(n);
        dp[0] = nums[0];
        int max_sum = nums[0];
        for(int i=1; i<n; i++) {
            if(dp[i-1]<0) dp[i] = nums[i];
            else dp[i] = dp[i-1] + nums[i];
            max_sum = max(max_sum, dp[i]);
        }

        return max_sum;
    }
};
```
![image](https://github.com/user-attachments/assets/eaaa538a-2d32-4f19-be27-fe6e26fd7c88)
