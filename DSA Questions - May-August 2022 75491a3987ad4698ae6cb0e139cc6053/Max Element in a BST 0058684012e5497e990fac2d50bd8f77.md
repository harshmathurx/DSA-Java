# Max Element in a BST

The max element in a BST is the right most element 

```java
public Node(Node root){
	while(root!=null){
		root = root.left;
	}
	return root;
}
```