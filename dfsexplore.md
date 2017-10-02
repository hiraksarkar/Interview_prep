Print out all the paths leading from root to leaf

```cpp
/**
 * Definition for a binary tree node.
 * struct TreeNode {
 *     int val;
 *     TreeNode *left;
 *     TreeNode *right;
 *     TreeNode(int x) : val(x), left(NULL), right(NULL) {}
 * };
 */
class Solution {
public:
    void subgraph(vector<string> &vec, TreeNode *t, string s){
        if(!t->left && !t->right){
            vec.push_back(s);
            return;
        }
        
        if(t->left) subgraph(vec,t->left,s+"->"+to_string(t->left->val));
        if(t->right) subgraph(vec,t->right,s+"->"+to_string(t->right->val));
    }
    
    vector<string> binaryTreePaths(TreeNode* root) {
        vector<string> vec;
        if (!root) return vec;
        
        subgraph(vec, root, to_string(root->val));
        return vec;
    }
};
```
