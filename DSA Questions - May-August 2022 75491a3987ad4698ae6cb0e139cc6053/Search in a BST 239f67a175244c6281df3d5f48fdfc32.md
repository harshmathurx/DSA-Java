# Search in a BST

[Search in a Binary Search Tree - LeetCode](https://leetcode.com/problems/search-in-a-binary-search-tree)

## Approach

 Base case - If root is null

you have reached the end of the tree

return null

- If root == key
    - return root
    
- if root is less than the key
    - return recursive call to the right subtree
    - this will either return a null or the node containing the answer
    - this will then be returned by our function

- If root is greater than the key
    - return recursive call to the left subtree
    - this will either return a null or the node containing the answer
    - this will then be returned by our function

**DEFAULT CASE:** 

return null

(when nothing is found)

```java
	public TreeNode searchBST(TreeNode root, int key) {
        if(root == null) return null;
        
        if(root.val == key) return root;
        
        if(root.val < key){
            return searchBST(root.right,key);
        }
        
        if(root.val > key){
            return searchBST(root.left,key);
        }
        
        return null;
    }
```