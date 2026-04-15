
# LeetCode 104. **Maximum Depth of Binary Tree**

## **Approach** - 
    - Use recursion (DFS): compute depth of left and right subtree, take max.
    - Base case: if node is NULL, return 0; else return 1 + max(left, right).


## **Code** -
    
```cpp
/**
 * Definition for a binary tree node.
 * struct TreeNode {
 *     int val;
 *     TreeNode *left;
 *     TreeNode *right;
 *     TreeNode() : val(0), left(nullptr), right(nullptr) {}
 *     TreeNode(int x) : val(x), left(nullptr), right(nullptr) {}
 *     TreeNode(int x, TreeNode *left, TreeNode *right) : val(x), left(left), right(right) {}
 * };
 */
class Solution {
public:
    int maxDepth(TreeNode* root) {
        if(!root) return 0;
        int maxLeft = maxDepth(root->left);
        int maxRight = maxDepth(root->right);
        return max(maxLeft, maxRight)+1;
    }
};
```
     
![Output Screenshot](AvniGoel_15-04-26_Day25.png)