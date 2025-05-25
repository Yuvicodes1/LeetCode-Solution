# 136. Single Number

✅ **Solved**  
📘 **Difficulty:** Easy  
🏷️ **Topics:** Hash Table, Bit Manipulation  
🏢 **Companies:** [Multiple]  

---

## 🧠 Problem Statement

Given a non-empty array of integers `nums`, every element appears **twice** except for **one**. Find that **single one**.

You must implement a solution with:
- **Linear runtime complexity**
- And use only **constant extra space**

## SOLUTIONS
**MAP**
```cpp
class Solution {
public:
    int singleNumber(vector<int>& nums) {
        int n=nums.size();
        map <int,int> mp;
        for (int i = 0; i < n; i++) {
            mp[nums[i]]++;
        }
        for(auto it:mp){
            if(it.second==1)
                return it.first;
        }
        return -1;
    }
};
```
![image](https://github.com/user-attachments/assets/ebf96a57-63cc-4392-9348-da8e35c8e88d)

**XOR - BEST APPROACH**
```cpp
class Solution {
public:
    int singleNumber(vector<int>& nums) {
        int xr=0;
        for(int i=0;i<nums.size();i++)
            xr=xr^nums[i];
        return xr;
    }
};
```
![image](https://github.com/user-attachments/assets/83949e2b-45df-49b0-b4b9-6f8113e61eed)
