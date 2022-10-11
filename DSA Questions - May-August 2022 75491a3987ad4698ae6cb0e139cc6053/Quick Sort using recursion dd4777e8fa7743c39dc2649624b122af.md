# Quick Sort using recursion

![Untitled](Quick%20Sort%20using%20recursion%20dd4777e8fa7743c39dc2649624b122af/Untitled.png)

## Idea

The idea of quick sort is to choose a pivot point at random and then place it at the right place i.e. at a point where all the elements to the left are smaller and all the elements to the right are greater.

Then we move to the next random element. I personally use the middle element.

We keep doing this until the array is sorted 

## Approach

To place the pivot element at the right place 

- Select the pivot element based on your method here we will take the middle element as the pivot element.
- Place 2 pointers s and e at the start and end of the array
- get your pivot

```java
public static void quickSort(int[] arr,int lo,int hi){
	    if(low>=hi){
	        return;
	    }
	    
	    int s = low;
	    int e = hi;
	    int m = s + (e-s)/2;
	    
	    int pivot = arr[m];
	    
	    while(s<=e){
	        while(arr[s] < pivot){
	            s++;
	        }
	        
	        while(arr[e] > pivot){
	            e--;
	        }
	        
	        if(s<=e){
	            int temp = arr[s];
	            arr[s] = arr[e];
	            arr[e] = temp;
	            s++;
	            e--;
	        }
	    }
	    
	    quickSort(arr,lo,e);
	    quickSort(arr,s,hi);
	}
```