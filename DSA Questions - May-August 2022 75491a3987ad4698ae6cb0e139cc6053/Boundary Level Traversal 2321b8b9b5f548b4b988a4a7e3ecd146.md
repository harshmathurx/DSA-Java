# Boundary Level Traversal

[https://www.youtube.com/watch?v=0ca1nvR0be4](https://www.youtube.com/watch?v=0ca1nvR0be4)

![Untitled](Boundary%20Level%20Traversal%202321b8b9b5f548b4b988a4a7e3ecd146/Untitled.png)

### Required order

**1 2 3 4 5 6 10 11 9 8 7 1**

Root - 1

Left Nodes - 2 3 4

Leaf Nodes - 5 6 10 11

Right Nodes - 9 8 7 

## Approach

For Left - Level order traversal 

For leaves - In order traversal 

For Right - Reverse Level order traversal 

```java
	static ArrayList < Integer > printBoundary(Node node) {

        ArrayList <Integer> ans = new ArrayList <Integer> ();

        if (isLeaf(node) == false) ans.add(node.data);

        addLeftBoundary(node, ans);
        addLeaves(node, ans);
        addRightBoundary(node, ans);

        return ans;
    }

		static Boolean isLeaf(Node root) {
        return (root.left == null) && (root.right == null);
    }
```

## For Left Nodes

- Start with root.left (because root is already in the result array)
- loop until the node is not null (you reach the leaf)
    - if node is not null
        - add to list
    - if left is not null
        - node = node.left
    - else
        - rode = node.right

```java
    static void addLeftBoundary(Node root, ArrayList < Integer > res) {
        Node cur = root.left;
        while (cur != null) {
            if (isLeaf(cur) == false) res.add(cur.data);
            if (cur.left != null) cur = cur.left;
            else cur = cur.right;
        }
    }
```

## For Right Nodes

- We use the same iterative approach as the one for the left boundary
- The only difference is that we add the integers to a temporary array
- After the iteration is complete
    - we add the integers of the temp to the result in a reverse order

```java
    static void addRightBoundary(Node root, ArrayList < Integer > res) {
        Node cur = root.right;
        ArrayList < Integer > tmp = new ArrayList < Integer > ();
        while (cur != null) {
            if (isLeaf(cur) == false) tmp.add(cur.data);
            if (cur.right != null) cur = cur.right;
            else cur = cur.left;
        }

				// add nodes to result in reverse order
        int i;
        for (i = tmp.size() - 1; i >= 0; --i) {
            res.add(tmp.get(i));
        }
    }
```

## For Leaf Nodes

- For the lead nodes, we use a recursive function
- Base case
    - if the node is a leaf
        - add node to result
- If left is not null
    - recursive call with left node
- If right is not null
    - recursive call with right node

```java
    static void addLeaves(Node root, ArrayList < Integer > res) {
        if (isLeaf(root)) {
            res.add(root.data);
            return;
        }
        if (root.left != null) addLeaves(root.left, res);
        if (root.right != null) addLeaves(root.right, res);
    }
```