# 283. Move Zeroes
LINK : https://leetcode.com/problems/move-zeroes/description/

## Problem Statement

Given an integer array `nums`, move all `0`'s to the end of it while maintaining the **relative order of the non-zero elements**.

You must do this **in-place** without making a copy of the array.

---

## Example 1:

**Input:**  
`nums = [0,1,0,3,12]`  
**Output:**  
`[1,3,12,0,0]`

---

## Example 2:

**Input:**  
`nums = [0]`  
**Output:**  
`[0]`

---

## Constraints:

- `1 <= nums.length <= 10^4`
- `-2^31 <= nums[i] <= 2^31 - 1`

---

##Solutions 
## 1. Solution 1 (NAIVE - O(N)) 
```cpp
class Solution {
public:
    void moveZeroes(vector<int>& nums) {
        int n=nums.size();
        for (int i=n-1;i>=0;i--){
            if(nums[i]==0){
                for(int j=i;j<n-1;j++){
                    nums[j]=nums[j+1];
                }
                nums[n-1]=0;
            }
        }
    }
}
```
![image](https://github.com/user-attachments/assets/ada50702-1810-4ae8-b2b9-e89db40f5e01)


## Solution 2 (Optimal approach - O(N))
```cpp
class Solution {
public:
    void moveZeroes(vector<int>& nums) {
        int n=nums.size();
        int j;
        for(int i=0;i<n-1;i++){
            if(nums[i]==0){
                j=i;
                break;
            }
        }

        for(int i=j+1;i<n;i++){
            if(nums[i]!=0){
                int temp=nums[j];
                nums[j]=nums[i];
                nums[i]=temp;
                j++;
            }
        }
    }
};
```
![image](https://github.com/user-attachments/assets/d16aba20-d676-426a-aacc-ade3a70adf53)

