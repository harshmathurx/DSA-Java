# Height of Tree

![Untitled](Height%20of%20Tree%20887ebed7a48b4a43a762df4150e397d1/Untitled.png)

Height of a tree = level of root - level of deepest leaf

```java
	public static int height(Node root){
        if(root == null){
            return 0;
        }

        int leftHeight = height(root.left);
        int rightHeight = height(root.right);

				//choosing the deepest leaf
        return Math.max(leftHeight, rightHeight) + 1;
    }
```