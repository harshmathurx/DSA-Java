# Ceil in a BST

[https://www.codingninjas.com/codestudio/problems/ceil-from-bst_920464?leftPanelTab=0](https://www.codingninjas.com/codestudio/problems/ceil-from-bst_920464?leftPanelTab=0)

## Approach

Keep a default ceil value of -1

Traverse in the tree until the node is null

There can exist 3 cases 

1. If the node is greater than the key
    
    this is a possible answer 
    
    store the node’s value in ceil
    
    Look to the left for a smaller value 
    
    (because we want the minimum value greater than the key)
    
2. If the node is smaller than the key
    
    Move right
    
    (this will not be an answer)
    
3. If the node is equal to the key
    
    return the node’s value 
    
    (because node ≥ key) and that’s what we want
    

```java
		public  static int findCeil(TreeNode<Integer> root, int key) {
        int ceil = -1;
        while(root != null){
            if(root.data == key){
                ceil = root.data;
                return ceil;
            }
            if(root.data > key){
                ceil = root.data;
                root = root.left;
            }
            else{
                root = root.right;
            }
        }
        return ceil;
    }
```