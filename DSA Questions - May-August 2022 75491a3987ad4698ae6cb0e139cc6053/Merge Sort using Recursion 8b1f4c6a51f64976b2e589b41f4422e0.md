# Merge Sort using Recursion

## The idea

Break down the array into smaller parts where the list either has 1 or 2 elements, so it is easier to sort

Use 2 functions

1. Merge
2. Sort

Sort is the recursive function to break down the array into smaller parts

The merge function merges the list based on the bigger number 

## Sort Function

- We find the middle element and sort the left and the right part of the array
- Then we merge the left and right arrays using the merge function

**Base Case**

If the array is only left with 1 element 

return the array 

```java
public static int[] mergeSort(int[] arr){
	    if(arr.length == 1) return arr;
	    
	    int mid = arr.length/2;
	    int[] left = mergeSort(Arrays.copyOfRange(arr,0,mid));
	    int[] right = mergeSort(Arrays.copyOfRange(arr,mid,arr.length));
	    
	    return merge(left,right);
	}

```

## The merge function

```java

	public static int[] merge(int[] first,int[] second){
	    int i = 0;
	    int j = 0;
	    int k = 0;
	    
	    int[] mix = new int[first.length + second.length];
	    
	    while(i<first.length && j < second.length){
	        if(first[i] > second[j]){
	            mix[k] = second[j];
	            j++;
	        } else {
	            mix[k] = first[i];
	            i++;
	        }
	        k++;
	    }
	    
	    while(i<first.length){
	        mix[k] = first[i];
	        i++;
	        k++;
	    }
	    while(j<second.length){
	        mix[k] = second[j];
	        j++;
	        k++;
	    }
	    
	    return mix;
	}
```