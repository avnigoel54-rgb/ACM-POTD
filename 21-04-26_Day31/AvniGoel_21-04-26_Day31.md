
# LeetCode 70. **Climbing Stairs**

## **Approach** - 
    - Uses an iterative dynamic programming approach where each step’s ways = sum of previous two (like Fibonacci).
    - Initialize two variables for base cases and update them in a loop up to `n`.
    - Achieves O(n) time and O(1) space by avoiding recursion and storing only last two results.


## **Code** -
    
```cpp
class Solution {
public:
    int climbStairs(int n) {
        if (n == 0 || n == 1) {
            return 1;
        }
        int prev = 1, curr = 1;
        for (int i = 2; i <= n; i++) {
            int temp = curr;
            curr = prev + curr;
            prev = temp;
        }
        return curr;
    }
};
```
     
![Output Screenshot](AvniGoel_21-04-26_Day31.png)
