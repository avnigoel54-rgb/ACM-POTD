
# LeetCode 543. **Diameter of Binary Tree**

## **Approach** - 
    - Compute the height of each subtree using DFS (postorder traversal).
    - At every node, update the diameter as the sum of left and right subtree heights (`l + r`).
    - Return `1 + max(l, r)` as height, while tracking the maximum diameter globally.


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
    int res = 0;
public:
    int diameterOfBinaryTree(TreeNode* root) {
        dfs(root);
        return res;        
    }
private:
    int dfs(TreeNode* root) {
        if (!root) return 0;
        int l = dfs(root->left);
        int r = dfs(root->right);
        res = max(res, l + r);
        return 1 + max(l, r);
    }    
};
```
     
![Output Screenshot](AvniGoel_17-04-26_Day27.png)
