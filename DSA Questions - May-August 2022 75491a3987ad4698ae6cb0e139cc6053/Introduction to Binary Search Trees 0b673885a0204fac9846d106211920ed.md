# Introduction to Binary Search Trees

## Binary Search Trees are modified versions of Binary Trees

## Time Complexity to search in a BST: O(H)

Where H is the height of the tree

In average cases, H is around log(N)

## Properties

- BST can have 2 children at every node

**IMP ⭐⭐**

- **The left child of a node in a BST is always less than the root**
- **The right child of a node in BST is always greater than the root**

### Left Child < Root < Right Child

![Untitled](Introduction%20to%20Binary%20Search%20Trees%200b673885a0204fac9846d106211920ed/Untitled.png)

The left and right subtrees of Binary Search Trees are also BSTs

Duplicates in a BST are debatable, it’s always nice to ask 

# Searching in a BST

- In order traversal of a BST gives us a sorted sequence

![Untitled](Introduction%20to%20Binary%20Search%20Trees%200b673885a0204fac9846d106211920ed/Untitled%201.png)

OUTPUT - 1, 2, 3, 4, 5, 6

Order of Traversal - Left → Root → Right 

- They are names Binary Search Trees for a reason
- Searching in a BST is almost like a binary search in a sorted array

Time Complexity of Searching in BST

Average - O(H), H is height of tree

Worst - O(N) - skewered trees or tree with a greater vertical length