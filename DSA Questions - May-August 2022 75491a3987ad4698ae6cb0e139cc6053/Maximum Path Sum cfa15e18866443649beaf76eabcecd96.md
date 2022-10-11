# Maximum Path Sum

[Binary Tree Maximum Path Sum - LeetCode](https://leetcode.com/problems/binary-tree-maximum-path-sum/)

## Approach

- Keep a global variable max to store the max value until now
- create a helper function which return the max path sum of the given root’s tree

[https://www.youtube.com/watch?v=WszrfSwMz58&list=PLgUwDviBIf0q8Hkd7bK2Bpryj2xVJk8Vk&index=18](https://www.youtube.com/watch?v=WszrfSwMz58&list=PLgUwDviBIf0q8Hkd7bK2Bpryj2xVJk8Vk&index=18)

## KEY

## At every node, we return the max path sum of that node

## We use the max variable to store the max of all path sums

Helper function 

- Recursively reach the left and right leaf nodes
- If the value of the recursive left and right calls is less than 0,
    - we store them as 0
    - because the max path sum will not be negative
        
         `left = Math.max(helper(root.left), 0);
         right = Math.max(helper(root.right), 0);`
        

- base case: if the root is null
    - return 0 (max sum at leaf node is 0 + root’s value)
- change the value of max to
    - `Math.max(current sum, max)`
    - **current sum = left subtree sum + right subtree sum + root val**

- We return the max path sum of the given node
- It is different from what is stored in the max variable
    
    `return root.val + Math.max(left, right)`
    

```java
		int max = Integer.MIN_VALUE;
    
    public int maxPathSum(TreeNode root) {
        helper(root);
        return max;
    }
    
    // helper returns the max branch 
    // plus current node's value
    public int helper(TreeNode root){
        if (root == null) return 0;
        
        int left = Math.max(helper(root.left), 0);
        int right = Math.max(helper(root.right), 0);
        
        max = Math.max(max, root.val + left + right);
        
        return root.val + Math.max(left, right);
    }
```