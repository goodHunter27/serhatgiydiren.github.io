---
title: Google Meta Amazon Coding Interview Question - Minimum Depth of Binary Tree
published: true
redirect_to: https://serhatgiydiren.com/google-meta-amazon-coding-interview-question-min-depth-binary-tree/
---

Find the minimum depth (depth of first leaf) of a binary tree.

```cpp
struct node
{
 node *left, *right;
 int val;
};

int min_depth(node* root)
{
 if (root == NULL) return 0;
 if (root->left == NULL) return min_depth(root->right) + 1;
 if (root->right == NULL) return min_depth(root->left) + 1;
 return 1 + min(min_depth(root->left), min_depth(root->right));
}
```
