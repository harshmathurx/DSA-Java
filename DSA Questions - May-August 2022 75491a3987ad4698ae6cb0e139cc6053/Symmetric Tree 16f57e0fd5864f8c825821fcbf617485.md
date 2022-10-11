# Symmetric Tree

[Symmetric Tree - LeetCode](https://leetcode.com/problems/symmetric-tree/)

![Untitled](Symmetric%20Tree%2016f57e0fd5864f8c825821fcbf617485/Untitled.png)

## Approach

- if any of the children of the root is null
    - check if they are equal
- if the left is not equal to the right
    - return false
- recursive call
    - left of left is equal to the right of right (mirror)
    - left of right is equal to the right of left (mirror)

```java
		public boolean isSymmetric(TreeNode root) {
        if(root == null) return true;
        
        return isSymmetric(root.left,root.right);
    }
    
    public boolean isSymmetric(TreeNode left,TreeNode right){
        if(left == null || right == null){
            return left == right;
        }
        
        if(left.val != right.val){
            return false;
        }
        
        return isSymmetric(left.left,right.right) && isSymmetric(left.right,right.left);
    }
```