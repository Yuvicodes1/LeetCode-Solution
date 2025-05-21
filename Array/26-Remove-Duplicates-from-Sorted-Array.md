# 26. Remove Duplicates from Sorted Array
LINK:https://leetcode.com/problems/remove-duplicates-from-sorted-array/

**Difficulty:** Easy  
**Tags:** Array, Two Pointers

---

## 📘 Problem

Given an integer array `nums` sorted in **non-decreasing** order, remove the **duplicates in-place** such that each unique element appears only once.  
The relative order of the elements should be kept the same.  

Then return the number of unique elements in `nums`.

---

### ✅ Constraints

- Modify the input `nums` **in-place**.
- You must **return `k`**, the number of unique elements.
- Only the first `k` elements matter; rest can be ignored.

---

### 🔹 Example
Input: nums = [1,1,2]  
Output: 2, nums = [1,2,_]

```cpp
//Approach 1
class Solution {
public:
    int removeDuplicates(vector<int>& nums) {
        set <int> st;
        int n= nums.size();
        for (int i=0;i<n;i++){
            st.insert(nums[i]);
        }
        vector <int> new_nums;
        for (int x:st){
            new_nums.push_back(x);
        }
        nums=new_nums;
        return (nums.size());
    }
};
```

```cpp
//Approach 2 : Inplace shifting :
class Solution {
public:
    int removeDuplicates(vector<int>& nums) {
        int n=nums.size();
        int k=1;
        int count=1;
        for (int i = 1;i<n;i++){
            if(nums[i]!=nums[k-1]){
                nums[k++]=nums[i];
                count++;
            }
        }
        return count;
    }
};
```
