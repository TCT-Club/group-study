#include <bits/stdc++.h> 

/************************************************************

    Following is the BinaryTreeNode class structure

    template <typename T>
    class BinaryTreeNode {
       public:
        T val;
        BinaryTreeNode<T> *left;
        BinaryTreeNode<T> *right;

        BinaryTreeNode(T val) {
            this->val = val;
            left = NULL;
            right = NULL;
        }
    };

************************************************************/
template <typename T>
vector<T> getLevelOrder(BinaryTreeNode<T> *root)
{
    vector<T> ans; 
    
    if(root == NULL) 
        return ans; 
        
    queue<BinaryTreeNode<T>*> q; 
    q.push(root); 
    
    while(!q.empty()) {
        BinaryTreeNode<T> *temp = q.front(); 
        q.pop(); 
        
        if(temp->left != NULL) 
            q.push(temp->left); 
        if(temp->right != NULL) 
            q.push(temp->right); 
            
        ans.push_back(temp->val); 
    }
    return ans; 
}
