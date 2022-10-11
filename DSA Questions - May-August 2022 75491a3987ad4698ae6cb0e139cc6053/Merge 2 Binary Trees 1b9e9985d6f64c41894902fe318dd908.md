# Merge 2 Binary Trees

[Merge Two Binary Trees - LeetCode](https://leetcode.com/problems/merge-two-binary-trees)

![Untitled](Merge%202%20Binary%20Trees%201b9e9985d6f64c41894902fe318dd908/Untitled.png)

## Approach

Create a brand new binary tree and construct it starting from the node 

This will be a recursive function because it returns Node

- If both the roots are null
    - We have reached the end
    - return null (this will set the new node to null, the one which called this particular function)
- To add a node to the tree, we need the sum of the roots
    - If in any of the trees, the node does not exist
    - put 0 there and get the sum
    - create the new node with the sum

`int v1 = root1 != null ? root1.val : 0;
 int v2 = root2 != null ? root2.val : 0;`

Recursive calls 

- If any of the roots is null
    - substitute it with null
    - make the recursive call

In the end, return the new root 

```java
	public TreeNode mergeTrees(TreeNode root1, TreeNode root2) {
        if(root1 == null && root2 == null){
            return null;
        }
        
        int v1 = root1 != null ? root1.val : 0;
        int v2 = root2 != null ? root2.val : 0;
        
        TreeNode root = new TreeNode(v1+v2);
        
        
        root.left = mergeTrees(((root1==null)? null : root1.left),((root2 == null)? null : root2.left));
        root.right = mergeTrees(((root1==null)? null : root1.right),((root2 == null)? null : root2.right));
        
        return root;
    }
```