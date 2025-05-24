# 🔢 Leetcode 485: Max Consecutive Ones

📎 **Link**: [https://leetcode.com/problems/max-consecutive-ones/](https://leetcode.com/problems/max-consecutive-ones/)

---

## 💭 Problem

Given a binary array `nums`, return the maximum number of consecutive `1`s in the array.

---

### Solution 
```cpp
class Solution {
public:
    int findMaxConsecutiveOnes(vector<int>& nums) {
        int max_count = 0, temp = 0;
        int n = nums.size();
        int i = 0;

        while (i < n) {
            if (nums[i] == 1) {
                temp++;
            } else {
                max_count = max(max_count, temp);
                temp = 0;
            }
            i++;
        }

        // Final check in case the array ends with 1s
        max_count = max(max_count, temp);

        return max_count;
    }
};
```


