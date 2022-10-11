# The subtree of another tree

The question is to check if a given tree is a subtree of a bigger tree

![Untitled](The%20subtree%20of%20another%20tree%204f13f9e8746e42d9a398d579b06796ce/Untitled.png)

## Edge Cases

- If the root of the subtree is null
    - Return true (null is always present in a tree)
- If the root of the tree is null
    - return false
    - (there is no tree)

## Checking if it is a subtree

- if the root of the subtree and the tree are equal
    - check if they are identical (given below)
        - return true

- recursive call
    
    ```java
    	public static boolean isSubtree(Node root,Node subRoot){
            if(subRoot == null){
                return true;
            }
    
            if(root == null){
                return false;
            }
    
            if(root.data == subRoot.data){
                if(isIdentical(root,subRoot)){
                    return true;
                }
            }
    
            return isSubtree(root.left,subRoot) || isSubtree(root.right,subRoot);
        }
    ```
    
    - checking if the root of the subtree is either equal to the left or the right node of the tree
    - `return isSubtree(root.left,subRoot) || isSubtree(root.right,subRoot);`

## Is Identical

- cover the edge cases
- base case
    - if the root and the subroot are null
        - return true
- if the root and the subroot are equal
    - call the function recursively
    - return `func(root.left,subroot.left) && func(root.right,subroot.right)`
- default
    - return false

```java

    public static boolean isIdentical(Node root,Node subRoot){
        if(root == null && subRoot == null){
            return true;
        }

        if(root == null || subRoot == null){
            return false;
        }

        if(root.data == subRoot.data){
            return isIdentical(root.left,subRoot.left) && isIdentical(root.right,subRoot.right);
        }

        return false;
    }
```