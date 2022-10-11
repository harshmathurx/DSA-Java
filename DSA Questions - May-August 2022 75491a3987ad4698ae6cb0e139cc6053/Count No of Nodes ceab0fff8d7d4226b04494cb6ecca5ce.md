# Count No. of Nodes

- Use recursion
- Calculate No. of nodes for left subtree
- Calculate No. of nodes for the right subtree
- Add 1 to them, because the root node

![Untitled](Count%20No%20of%20Nodes%20ceab0fff8d7d4226b04494cb6ecca5ce/Untitled.png)

![Untitled](Count%20No%20of%20Nodes%20ceab0fff8d7d4226b04494cb6ecca5ce/Untitled%201.png)

![Untitled](Count%20No%20of%20Nodes%20ceab0fff8d7d4226b04494cb6ecca5ce/Untitled%202.png)

```java
public static int countNodes(Node root){
        if(root == null){
            return 0;
        }

        int leftNodes = countNodes(root.left);
        int rightNodes = countNodes(root.right);

        return leftNodes + rightNodes + 1;
    }
```

# Time Complexity - O(N)