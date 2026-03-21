# LeetCode 26. **Remove Duplicates from Sorted Array**

## **Approach** - 
    -implemented a variable(i) to track the last distinct element in the array
    -shifted the next distinct element to i+1-th index

## **Code** -
    
```cpp
    class Solution {
    public:
        int removeDuplicates(vector<int>& nums) {
            int n=nums.size();
            int i=0;
            for(int j=1;j<n;j++){
                if(nums[j]!=nums[i]){
                    nums[i+1]=nums[j]; 
                    i++;
                }
            }
            return i+1;
        }
    };
```

![Output Screenshot](POTD solution screenshots/day1.png)
