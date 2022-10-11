# Min Element in a BST

- The left mode node in a BST is the min element

```java
	int minvalue(Node node) {
        Node current = node;
  
        /* loop down to find the leftmost leaf */
        while (current.left != null) {
            current = current.left;
        }
        return (current.data);
    }
```