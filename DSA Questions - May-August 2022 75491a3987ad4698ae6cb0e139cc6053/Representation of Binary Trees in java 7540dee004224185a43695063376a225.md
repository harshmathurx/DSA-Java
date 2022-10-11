# Representation of Binary Trees in java

## Node Class

The node class contains 

- data
- left node
- right node
    
    ### Constructor
    
    - The default constructor of the node class has
    - int data
    - null left and right pointer

```java
static class Node {
        int data;
        Node left;
        Node right;

        public Node(int data){
            this.data = data;
            this.left = null;
            this.right = null;
        }
    }
```

## Preorder tree building (Recursively)

- -1 represents null
- Traverse in the array of elements
- Create a node for every element

To fill a tree

- First fill left subtree
- Then fill right subtree

Example 

 Input - [1 ,2 , 4, -1, -1, -1, 5, -1, -1, 3, -1, 6, -1 ,-1]

/

[https://youtu.be/-DzowlcaUmE?t=696](https://youtu.be/-DzowlcaUmE?t=696)

![Untitled](Representation%20of%20Binary%20Trees%20in%20java%207540dee004224185a43695063376a225/Untitled.png)

---

## **Code**

Recursive Function 

- Base case: if you find an element as null, return
    - Then we return to the parent node
    - and continue filling the tree
- Create a variable to iterate in the array
- Increase the count of the iterator by 1 at every call

- Create a new code with the value of i element
- assign the value of the left node with a recursive all
    - (this will execute until the left subtree is formed)
- Then assign the value of the right node with a recursive call
- return the root node

```java
public static Node buildTree(int[] nodes){
        idx++;
        if(nodes[idx] == -1){
           return null;
        }

        Node newNode = new Node(nodes[idx]);
        newNode.left = buildTree(nodes);
        newNode.right = buildTree(nodes);

        return newNode;
    }
```