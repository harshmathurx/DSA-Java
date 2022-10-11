# Heapify

## The idea is to take a node as input and place it at it’s correct position

In the end we need to assure the tree is a heap

## Approach

- Find the node with the largest value
    - It will either be left child, right child or the ith node
- If the largest is not ith node
    - the tree is not a heap
    - swap the largest node with the ith node
    - call the function recursively on the largest node
    - (this is to ensure all the other nodes follow the properties of a heap)

```java
	public static void maxHeapify(int[] arr,int n,int i){
        int largest = i; // by default
        int leftChild = 2*i;
        int rightChild = (2*i) + 1;

        if(leftChild <= n && arr[largest] < arr[leftChild]){
            largest = leftChild;
        }
        if(rightChild <= n && arr[largest] < arr[rightChild]){
            largest = rightChild;
        }

        if(largest != i ){
            swap(arr,largest,i);
            maxHeapify(arr,n,largest);
        }
    }
```