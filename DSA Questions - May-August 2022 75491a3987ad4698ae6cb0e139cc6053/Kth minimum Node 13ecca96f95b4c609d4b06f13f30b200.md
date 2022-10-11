# Kth minimum Node

[Kth Smallest Element in a BST - LeetCode](https://leetcode.com/problems/kth-smallest-element-in-a-bst/)

## What we know

The in order traversal of a BST gives us a sorted order of the nodes 

## Approach

Store the in-order traversal of the tree in a list

return the k-1th node 

(because the desired output is 1 based indexing) 

```java
public int kthSmallest(TreeNode root, int k) {
        List<Integer> list = inorderTraversal(root);
        
        return list.get(k-1);
    }
    
    public List<Integer> inorderTraversal(TreeNode root) {
        List<Integer> res = new ArrayList<Integer>();
        if(root != null){
            res.addAll(inorderTraversal(root.left));
            res.add(root.val);
            res.addAll(inorderTraversal(root.right));
        }
        return res;
    }
```