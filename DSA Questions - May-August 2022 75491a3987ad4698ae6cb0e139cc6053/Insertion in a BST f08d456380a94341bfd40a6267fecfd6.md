# Insertion in a BST

[Insert into a Binary Search Tree - LeetCode](https://leetcode.com/problems/insert-into-a-binary-search-tree)

## Approach

- Define a recursive function which returns a node

Base Case

If the node is null, create a node and return it 

(this will be initialized when you reach a leaf and the left or right of the leaf is null)

- If the root is greater than the key
    - go to the left subtree
    - `root.left = insert(root.left,key)`
    - this will set the left after returning the modified tree
- If the root is less than the key
    - go to the right subtree
    - `root.right = insert(root.right,key)`
    - this will set the right after returning the modified tree

In the end, return the root node 

```java
		public TreeNode insertIntoBST(TreeNode root, int val) {
        if(root == null){
            root = new TreeNode(val);
        }
        
        if(root.val > val){
            //go left, returns the changes left subtree
            root.left = insertIntoBST(root.left,val);
        }
        
        if(root.val < val){
            root.right = insertIntoBST(root.right,val);
        }
        
        return root;
		}
```