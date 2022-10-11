# Delete a node in BST

[Delete Node in a BST - LeetCode](https://leetcode.com/problems/delete-node-in-a-bst/)

![Untitled](Delete%20a%20node%20in%20BST%203d7f131ae89d4eeb91e5df43c328a0aa/Untitled.png)

## To delete a node in a BST

1. Search the node in the BST
2. Find if the Node is which one of the below cases
3. Act on it 
4. Return the root after deletion

## There can be 3 possibilities of a node in a BST

A node can have 

1. No children (Leaf Node)
2. 1 Child
3. 2 Children

## When the node has

**No children or a leaf node** 

return null

The connection from the parent node will be broken

The leftover values will be removed by the garbage collector

**1 Child** 

![Untitled](Delete%20a%20node%20in%20BST%203d7f131ae89d4eeb91e5df43c328a0aa/Untitled%201.png)

```java
            if(root.left==null){
                return root.right;
            }
            else if(root.right == null){
                return root.left;
            }
```

This returns the updated subtree at the root node 

Here, it removes 11 and sets `root.right` to 14

**2 Children**

![Untitled](Delete%20a%20node%20in%20BST%203d7f131ae89d4eeb91e5df43c328a0aa/Untitled%202.png)

1. In this case, we find the inorder successor for node’s right
    1. why right? because the successor is greater than right
    2. In a BST, greater elements lie to the right of the root
2. Replace the node’s right with the next inorder successor 
3. Delete the inorder successor from it’s original place

To find the Inorder successor 

- Find the left-most node in the right subtree

```java
    public static TreeNode inOrderSuccessor(TreeNode root){
        while(root.left != null){
            root = root.left;
        }
        
        return root;
    }
```

```java
		public TreeNode deleteNode(TreeNode root, int key) {
        
        if(root == null) return root;
        
        //searching for the node
        if(root.val > key){
            root.left = deleteNode(root.left,key);
        }
        
        else if(root.val < key){
            root.right = deleteNode(root.right,key);
        }
        
        //found the node 
        if(root.val == key){
            
            //case 1 // leaf node
            if(root.left == null && root.right == null){
                return null;
            }
            
            //case 2
            if(root.left==null){
                return root.right;
            }
            else if(root.right == null){
                return root.left;
            }
            
            //case 3 // node has 2 children
            //replace node with in order successor 
            TreeNode IS = inOrderSuccessor(root.right);
            root.val = IS.val;
            //delete original inorder successor
            //This will only use case 1 and case 2
            root.right = deleteNode(root.right,IS.val);
        }
        return root;
    }
```