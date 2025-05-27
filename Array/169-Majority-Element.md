# 169. Majority Element

https://leetcode.com/problems/majority-element/submissions/1645979934/

**Difficulty:** Easy  
**Tags:** Array, Hash Table, Divide and Conquer, Sorting, Counting  
**Companies:** [Premium Lock]

## Problem Statement

Given an array `nums` of size `n`, return the **majority element**.

The **majority element** is the element that appears **more than ⌊n / 2⌋ times**.  
You may assume that the majority element **always exists** in the array.

---

## Solution

**BRUTE FORCE**
```cpp
class Solution {
public:
    int majorityElement(vector<int>& nums) {
        int n=nums.size();
        for(int i=0;i<n;i++){
            int freq=0;
            for(int j=i;j<n;j++){
                if(nums[i]==nums[j])
                    freq++;
            }
            if(freq>(n/2)) return nums[i];
        }
        return 0;
    }
};
```
![image](https://github.com/user-attachments/assets/0d71fd5f-2a19-422e-a18d-65ba9b65fd5c)

**Better approach using maps/hashing**
C++
```cpp
class Solution {
public:
    int majorityElement(vector<int>& nums) {
        int n=nums.size();
        map <int,int> mp;
        for(int i=0;i<n;i++){
            mp[nums[i]]++;
        }
        for(auto it:mp){
            if(it.second>(n/2))
                return it.first;
        } 
        return -1; //not found such element   
    }
};
```
![image](https://github.com/user-attachments/assets/3d8bbb82-b250-4b6a-a9f9-f509f9884580)


