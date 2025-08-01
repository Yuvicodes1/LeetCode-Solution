#Product of array except self

Given an integer array nums, return an array answer such that answer[i] is equal to the product of all the elements of nums except nums[i].

The product of any prefix or suffix of nums is guaranteed to fit in a 32-bit integer.

You must write an algorithm that runs in O(n) time and without using the division operation.

 

Example 1:

Input: nums = [1,2,3,4]
Output: [24,12,8,6]
Example 2:

Input: nums = [-1,1,0,-3,3]
Output: [0,0,9,0,0]

Link : https://leetcode.com/problems/product-of-array-except-self/description/

# Code

## 1 Brute Force gives TLE
```cpp
class Solution {
public:
    vector<int> productExceptSelf(vector<int>& nums) {
        int n=nums.size();
        vector<int> ans(n,0);

        for(int i = 0;i<n;i++){
            long product=1;
            for(int j=0;j<n;j++){
                if(j!=i)
                    product=product*nums[j];
            }
            ans[i]=product;
        }
        return ans;
    }
};
```

## 2 Division Approach 
