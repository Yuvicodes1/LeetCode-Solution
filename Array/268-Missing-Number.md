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
