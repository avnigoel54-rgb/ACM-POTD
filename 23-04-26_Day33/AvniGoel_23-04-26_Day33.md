
# LeetCode 746. **Min Cost Climbing Stairs**

## **Approach** - 
    - Treat each step’s cost as the minimum cost to reach that step by adding the current cost with the minimum of the previous two steps.
    - Update the array in-place: `cost[i] += min(cost[i-1], cost[i-2])`.
    - Final answer is the minimum of the last two steps since you can reach the top from either.



## **Code** -
    
```cpp
class Solution {
public:
    int minCostClimbingStairs(vector<int>& cost) {
        int n=cost.size();
        for(int i=2;i<n;i++)
        {
            cost[i]+=min(cost[i-1],cost[i-2]);
        }
        return min(cost[n-1],cost[n-2]);
    }
};
```
     
![Output Screenshot](AvniGoel_23-04-26_Day33.png)
