# Floor in a BST

[https://www.codingninjas.com/codestudio/problems/floor-from-bst_920457?leftPanelTab=1](https://www.codingninjas.com/codestudio/problems/floor-from-bst_920457?leftPanelTab=1)

## Approach

Keep a default ceil value of -1

Traverse in the tree until the node is null

There can exist 3 cases 

1. If the node is greater than the key
    
    Move right
    
    (this will not be an answer)
    
2. If the node is smaller than the key
    
    this is a possible answer 
    
    store the node’s value in ceil
    
    Look to the left for a smaller value 
    
    (because we want the minimum value greater than the key)
    

1. If the node is equal to the key
    
    return the node’s value 
    
    (because node ≥ key) and that’s what we want
    

```java
		public static int floorInBST(TreeNode<Integer> root, int key) {
        int floor = Integer.MAX_VALUE;
        while(root != null){
            if(root.data == key) return root.data;
            
            if(root.data > key){
                root = root.left;
            }
            else{
                floor = root.data;
                root = root.right;
            }
        }
        return floor;
    }
```