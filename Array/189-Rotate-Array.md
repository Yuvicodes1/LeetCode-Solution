# 189. Rotate Array

## 📝 Problem

Given an integer array `nums`, rotate the array to the right by `k` steps, where `k` is non-negative.

[Link to LeetCode Problem](https://leetcode.com/problems/rotate-array)

---



## ✅ Constraints

- `1 <= nums.length <= 10^5`
- `-2^31 <= nums[i] <= 2^31 - 1`
- `0 <= k <= 10^5`

---

## 🧠 Approach 1: Brute Force (Time Limit Exceeded for large k)

```cpp
class Solution {
public:
    void rotate(vector<int>& nums, int k) {
        int n = nums.size();
        for (int i = 0; i < k; i++) {
            int temp = nums[n - 1];
            for (int j = n - 1; j > 0; j--) {
                nums[j] = nums[j - 1];
            }
            nums[0] = temp;
        }
    }
};
```
## Approach 2 : Reverse array method
```cpp
class Solution {
public:
    void rotate(vector<int>& nums, int k) {
        int n = nums.size();
        k %= n; // Handle cases where k > n

        // Step 1: Reverse the whole array
        reverse(nums.begin(), nums.end());

        // Step 2: Reverse the first k elements
        reverse(nums.begin(), nums.begin() + k);

        // Step 3: Reverse the remaining elements
        reverse(nums.begin() + k, nums.end());
    }
};
```

