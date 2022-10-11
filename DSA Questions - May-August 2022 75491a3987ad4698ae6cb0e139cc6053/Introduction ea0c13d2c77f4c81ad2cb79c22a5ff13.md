# Introduction

A heap is a **Complete Binary Tree**

![Untitled](Introduction%20ea0c13d2c77f4c81ad2cb79c22a5ff13/Untitled.png)

There are 2 types of Heaps

- Max Heap
- Min Heap

Max Heap - A max-heap is a complete binary tree in which the value in each internal node is greater than or equal to the values in the children of that node.

![Untitled](Introduction%20ea0c13d2c77f4c81ad2cb79c22a5ff13/Untitled%201.png)

Min Heap (Exactly ulta) - A Min Heap Binary Tree is a Binary Tree where the root node has the minimum key in the tree.

![Untitled](Introduction%20ea0c13d2c77f4c81ad2cb79c22a5ff13/Untitled%202.png)

## Heap as an Array

Heap can be represented as an array by its level order traversal

![Untitled](Introduction%20ea0c13d2c77f4c81ad2cb79c22a5ff13/Untitled%203.png)

If a Node is at ith index in an array (1-based indexing)

Node - i

Node’s parent - $i/2$

Node’s left child - $(i*2)$

Node’s right child - $(i*2)+1$

## Heap Class

The heap class will have 2 components

1. Array as heap
2. size of the array

Constructor

The constructor will initialize a heap object with

1. An array with a size of 100
2. First element of the array as -1 (1-based indexing)
3. Size = 0 

```java
		public static class MaxHeap{
        int[] arr;
        int size;

        public MaxHeap(){
            arr = new int[100];
            arr[0] = -1;
            size = 0;
        }
    }
```

## Print Heap

```java
			public void print(){
            for(int i=1;i<=size;i++){
                System.out.print(arr[i] + " ");
            }
            System.out.println();
        }
```