# 🎨 Leetcode 75: Sort Colors

📎 **Link:** [https://leetcode.com/problems/sort-colors/](https://leetcode.com/problems/sort-colors/)

---

## 🧠 Problem Statement

Given an array `nums` with `n` objects colored red, white, or blue, sort them **in-place** so that objects of the same color are adjacent, with the colors in the order **red**, **white**, and **blue**.

We use the integers:
- `0` to represent red,
- `1` to represent white,
- `2` to represent blue.

You **must not** use the library’s sort function.

---

![image](https://github.com/user-attachments/assets/bd6a9023-bef0-4d16-a711-773b4b531d2d)

## SOLUTION 
1. **USING IN-PLACE SORTING ALGO**
```cpp
class Solution {
public:
    void sortColors(vector<int>& nums) {
        int n=nums.size();
        for(int i=0;i<n;i++){
            int min=i;
            for(int j=i+1;j<n;j++){
                if(nums[j]<nums[min]){
                    min=j;
                }
            }
            int t=nums[min];
            nums[min]=nums[i];
            nums[i]=t;
        }
    }
};
```
![image](https://github.com/user-attachments/assets/84933da3-7832-4aa0-b61e-9a7ca3498f81)
   

2.**Alternate Solution**
```cpp
class Solution {
public:
    void sortColors(vector<int>& nums) {
        int c_0=0,c_1=0,c_2=0;
        for(int i=0;i<nums.size();i++){
            if(nums[i]==0) c_0++;
            if(nums[i]==1) c_1++;
            if(nums[i]==2) c_2++;
        }
        nums.clear();
        while(c_0!=0){
            nums.push_back(0);
            c_0--;
        }
        while(c_1!=0){
            nums.push_back(1);
            c_1--;
        }
        while(c_2!=0){
            nums.push_back(2);
            c_2--;
        }
    }
};
```
![image](https://github.com/user-attachments/assets/7c8d4a0b-a6ed-4e3c-902a-e0fb0302b85f)
