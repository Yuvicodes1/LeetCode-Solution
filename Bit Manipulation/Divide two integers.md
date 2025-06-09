https://leetcode.com/problems/divide-two-integers/submissions/1658943050/

```cpp
class Solution {
public:
    int divide(int dividend, int divisor) {

        // Handle overflow case
        if (dividend == INT_MIN && divisor == -1)
            return INT_MAX;

        // Convert both numbers to long to prevent overflow. learn labs();
        long long dvd = labs(dividend);
        long long dvs = labs(divisor);
        long long result = 0;

        while (dvd >= dvs) {
            long long temp = dvs, multiple = 1;
            while (dvd >= (temp << 1)) {
                temp <<= 1;
                multiple <<= 1;
            }
            dvd -= temp;
            result += multiple;
        }

        // Determine the sign of the result
        if ((dividend < 0) ^ (divisor < 0))
            result = -result;

        return result;
    }
};
```
![image](https://github.com/user-attachments/assets/6027ac9e-42f2-411e-9464-9eedd95b645a)
