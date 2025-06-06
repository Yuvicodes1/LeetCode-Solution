
![image](https://github.com/user-attachments/assets/e3cfd7e1-5f97-42cb-8a57-e634f5876f62)

# Two Pointer ans Sorting Approach

![image](https://github.com/user-attachments/assets/32121300-061f-41aa-928f-bcf0264e143d)

```cpp
class Solution {
public:
    int threeSumClosest(vector<int>& nums, int target) {
        sort(nums.begin(),nums.end());
        int diff=INT_MAX;
        int ans=0;
        int n=nums.size();
        for(int i=0;i<n;i++){
            while(i<n-1 && nums[i]==nums[i+1]) continue;
            int j=i+1;
            int k=n-1;
            while(j<k){
                int sum=nums[i]+nums[j]+nums[k];
                int temp_diff=abs(target-sum);
                if(temp_diff<diff){
                    diff=temp_diff;
                    ans=sum;
                }
                if (sum < target) {
                    j++;
                } else if (sum > target) {
                    k--;
                } else {
                    // Exact match found
                    return target;
                }
            }
        }
        return ans;
    }
};
```

You're always moving both pointers, which defeats the purpose of the two-pointer strategy.

In a two-pointer approach, you should:

Increase j when sum < target

Decrease k when sum > target

Adjust both only when sum == target

