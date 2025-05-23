```cpp
class Solution {
public:
    int missingNumber(vector<int>& nums) {
        int n=nums.size();
        int sum=(n*(n+1))/2;
        int sc=0;
        for(int i=0;i<n;i++){
            sc+=nums[i];
        }
        return (sum-sc);
    }
};
```
```cpp
//BRUTE FORCE SOLUTION 
class Solution {
public:
    int missingNumber(vector<int>& nums) {
        int n = nums.size();
        int flag = 0;
        for (int i = 0; i <= n; i++) {  // Check from 0 to n inclusive
            flag = 0;
            for (int j = 0; j < nums.size(); j++) {
                if (nums[j] == i) {     // Check if i exists in nums
                    flag = 1;
                    break;
                }
            }
            if (flag == 0) return i;   // If i not found in nums, return it
        }
        return -1; // Should never reach here
    }
};
```
