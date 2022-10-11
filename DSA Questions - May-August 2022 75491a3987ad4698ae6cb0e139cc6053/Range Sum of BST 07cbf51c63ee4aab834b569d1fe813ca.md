# Range Sum of BST

[Range Sum of BST - LeetCode](https://leetcode.com/problems/range-sum-of-bst)

The question is almost the same as 

[Print in range](Print%20in%20range%20281aca56947446ca8fdde05b48d39e51.md)

```java
		public int rangeSumBST(TreeNode root, int X, int Y) {
        if(root == null){
            return 0;
        }
        int sum = 0;
        
        if(root.val >= X && root.val <= Y){
            sum += rangeSumBST(root.left,X,Y);
            sum += root.val;
            sum += rangeSumBST(root.right,X,Y);
        }
        
        else if(root.val >= Y){
            sum += rangeSumBST(root.left,X,Y);
        }
        else{
            sum += rangeSumBST(root.right,X,Y);
        }
        return sum;
    }
```