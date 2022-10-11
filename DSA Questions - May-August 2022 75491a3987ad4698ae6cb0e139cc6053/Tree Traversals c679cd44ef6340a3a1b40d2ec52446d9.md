# Tree Traversals

There are 2 types of tree traversals

- Depth-first search
- Breadth-First Search

## BFS

### Pre-order Traversal

The order of visiting nodes 

1. Root 
2. Left Subtree
3. Right Subtree

```java
		public static void preorder(Node root){
        if(root == null || root.data == -1){
            return;
        }

        System.out.println(root.data + " ");

        preorder(root.left);
        preorder(root.right);
    }
```

```java
1 
2 
4 
5 
3 
6
```

### In order Traversal

The order of visiting nodes 

1. Left Subtree
2. Root
3. Right Subtree

```java
		public static void inorder(Node root){
        if(root == null || root.data == -1){
            return;
        }
        inorder(root.left);
        System.out.println(root.data + " ");
        inorder(root.right);
    }
```

```java
4 
2 
5 
1 
3 
6
```

### Post order Traversal

The order of visiting nodes 

1. Left Subtree
2. Right Subtree
3. Root

```java
		public static void postorder(Node root){
        if(root == null || root.data == -1){
            return;
        }
        postorder(root.left);
        postorder(root.right);
        System.out.println(root.data + " ");
    }
```

```java
4 
5 
2 
6 
3 
1
```

## DFS

### Level order Traversal

## **Code**

```java
public static void levelOrder(Node root){
        Queue<Node> q = new LinkedList<Node>();
        q.add(root);
        q.add(null);
        while(!q.isEmpty()){
            Node curr = q.remove();

            if(curr != null){
								System.out.print(curr.data + " ");
                if(curr.left != null){
                    q.add(curr.left);
                }
                if(curr.right != null){
                    q.add(curr.right);
                }
            }

            else{
                System.out.println();
                if(q.isEmpty()){
                    break;
                }
                else{
                    q.add(null);
                }
            }
        }
    }
```