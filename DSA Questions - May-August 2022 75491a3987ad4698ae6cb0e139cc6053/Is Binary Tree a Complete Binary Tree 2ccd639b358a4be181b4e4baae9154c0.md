# Is Binary Tree a Complete Binary Tree

[Check Completeness of a Binary Tree - LeetCode](https://leetcode.com/problems/check-completeness-of-a-binary-tree/)

## Parameters to Check

- The no. of nodes in the tree

```java
		public int treeCount(TreeNode root){
        if(root == null){
            return 0;
        }
        int left = treeCount(root.left);
        int right = treeCount(root.right);
        return left+right+1;
    }
    
    public boolean isCBT(TreeNode root, int i, int count){
        if(root == null){
            return true;
        }
        
        if(i > count){
            return false;
        }
        else {
            return (isCBT(root.left,(2*i),count) && isCBT(root.right,((2*i)+1),count)); 
        }
    }

    public boolean isCompleteTree(TreeNode root) {
        int count = treeCount(root);
        return isCBT(root,1,count);
    }
```