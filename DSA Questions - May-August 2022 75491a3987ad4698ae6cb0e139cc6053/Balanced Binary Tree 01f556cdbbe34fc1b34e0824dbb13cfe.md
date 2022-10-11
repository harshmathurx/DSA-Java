# Balanced Binary Tree

[Balanced Binary Tree - LeetCode](https://leetcode.com/problems/balanced-binary-tree/)

## Idea

- For a balance binary tree
- **left height - right height ≤ 1**

## Naive Approach

- Visit every node recursively
- Check the left and the right height
- If the left - right > 1
    - return false
- Recursively call for the left and right node (to reach the leaf node)
- If even 1 of the recursive calls returns false
    - return false
- Otherwise return true

Time Complexity - $O(N^2)$

## Code

```java
public boolean isBalanced(TreeNode root) {
        if(root == null){
            return true;
        }
        
        int left = height(root.left);
        int right = height(root.right);
        
        if(Math.abs(left-right) > 1) return false;
        
        boolean isLeft = isBalanced(root.left);
        boolean isRight = isBalanced(root.right);
        
        if(!isLeft || !isRight) return false;
        
        return true;
    }
```

## Optimized Solution

Change the height function a little bit

- Check if the tree is balanced the height function using  `if(Math.abs(left - right) > 1)`
    - if it it not balanced return -1
    - else return the height

- This will recursively reach the root node and we can check
- At the root node, if the returned value is -1
    - return false;
- Else return true

```java
		public boolean isBalanced(TreeNode root) {
        return dfsHeight(root) != -1;
    }
    
    public int dfsHeight(TreeNode root){
        if(root == null) return 0;
        
        int left = dfsHeight(root.left);
        int right = dfsHeight(root.right);
        
        if(left == -1 || right == -1) return -1;
        
        if(Math.abs(left - right) > 1) return -1;
        
        return Math.max(left,right) + 1; 
  
```

## Time complexity - O(N)