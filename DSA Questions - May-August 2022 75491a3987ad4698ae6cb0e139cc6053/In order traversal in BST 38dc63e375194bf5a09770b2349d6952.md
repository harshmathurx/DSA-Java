# In order traversal in BST

Same as 

[Tree Traversals](Tree%20Traversals%20c679cd44ef6340a3a1b40d2ec52446d9.md)

```java
public void inOrder(Node root){
	if(root == null) return;

	inOrder(root.left);
	System.out.print(root.val," ");
	inOrder(root.right);
}
```