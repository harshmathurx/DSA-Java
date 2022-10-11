# Reverse an array using recursion

## Approach

- Use 2 pointer method
- Keep swapping them
- from left and right

```java
public static int[] rev(int[] arr, int l, int r){
	    if(l>=r){
	        return arr;
	    }
	    
	    int temp = arr[l];
	    arr[l] = arr[r];
	    arr[r] = temp;
	    
	    return rev(arr,l+1,r-1);
	}
```