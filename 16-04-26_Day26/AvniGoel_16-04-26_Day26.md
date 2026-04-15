
# LeetCode 226. **Invert Binary Tree**

## **Approach** - 
    - Swap the left and right child of each node, then recursively apply the same process to both subtrees.
    - Base case: if the node is `NULL`, return it; otherwise return the root after inversion.

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
    TreeNode* invertTree(TreeNode* root) {
        if (root == NULL) return NULL;
        TreeNode* temp = root->left;
        root->left = root->right;
        root->right = temp;
        invertTree(root->left);
        invertTree(root->right);
        return root;        
    }
};
```
     
![Output Screenshot](AvniGoel_16-04-26_Day26.png)
