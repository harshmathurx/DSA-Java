# Build Heap from the given array

## Approach

- The idea is to select every element from the back and check if it is in the correct position or not
- This will be done using Max Heapify

- In the implementation, we only heapify 0 to n/2 nodes
- because the remaining nodes n/2+1 to n are leaf nodes
- Leaf nodes are already heaps, so we do not need to check them

```java
				int[] arr = {-1,54,53,55,52,50};
        int n = 5;
        for(int i=n/2;i>0;i--){
            maxHeapify(arr,n,i);
        }
```

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