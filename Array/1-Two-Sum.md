# 🧮 Two Sum

**Leetcode Problem:** [1. Two Sum](https://leetcode.com/problems/two-sum/)  
**Difficulty:** Easy  
**Topics:** Array, Hash Table  
**Companies:** Amazon, Google, Facebook, Apple  

---

## 📝 Problem Statement

Given an array of integers `nums` and an integer `target`, return indices of the two numbers such that they add up to `target`.

You may assume that each input would have exactly one solution, and you may not use the same element twice.

You can return the answer in any order.

---

## 🔍 Example

### Example 1:
Input: nums = [2,7,11,15], target = 9
Output: [0,1]
Explanation: Because nums[0] + nums[1] == 9, we return [0, 1].

## Solution 

**BRUTE FORCE**
C++
```cpp
//BRUTE FORCE
class Solution {
public:
    vector<int> twoSum(vector<int>& nums, int target) {
        int n=nums.size();
        vector <int> ans;
        for(int i=0;i<n-1;i++){
            for(int j=i+1;j<n;j++){
                if(nums[i]+nums[j]==target){
                    ans.push_back(i);
                    ans.push_back(j);
                    return ans;
                }
            }
        }
        return ans;
    }
};
```
![image](https://github.com/user-attachments/assets/e4638306-f617-4a93-8348-d897fb416a77)

C
```c
/**
 * Note: The returned array must be malloced, assume caller calls free().
 */
int* twoSum(int* nums, int numsSize, int target, int* returnSize) {
    int* result=(int*) malloc(2*sizeof(int));
    *returnSize=2;
    for (int i=0;i<numsSize;i++){
        for (int j=1;j<numsSize;j++){
            if(j!=i){
                if(nums[i]+nums[j]==target){
                    result[0]=i;
                    result[1]=j;
                    return result;
                }
            }    
        }
    }
result[0]=0;
result[1]=1;
return result;
}
```
![image](https://github.com/user-attachments/assets/60463ce4-965e-4755-ab6c-234e4cbc8bc0)

**HASHING**

C++
```cpp
class Solution {
public:
    vector<int> twoSum(vector<int>& nums, int target) {
        int n=nums.size();
        unordered_map<int,int> mp;
        vector <int> ans;
        for(int i=0;i<n;i++){
            int rem=target-nums[i];
            if(mp.find(rem)!=mp.end()){
                ans.push_back(i);
                ans.push_back(mp[rem]);
                return ans;
            }
            mp[nums[i]]=i;
        }
        return ans;
    }
};
```
![image](https://github.com/user-attachments/assets/b6972b64-3d3b-4ded-b76e-8c3e8c041ae0)

**TWO POINTER**

C++
```cpp
class Solution {
public:
    vector<int> twoSum(vector<int>& nums, int target) {
        unordered_map<int, int> mp; // value -> index
        for (int i = 0; i < nums.size(); i++) {
            int complement = target - nums[i];
            if (mp.find(complement) != mp.end()) {
                return {mp[complement], i};
            }
            mp[nums[i]] = i;
        }
        return {}; // Should never reach here if exactly one solution exists
    }
};
```


