# Bubble sort using recursion

## The idea

- We check if the adjacent element is greater or not and if it is, we swap them.
- After every iteration of bubble sort, the goal is to make the largest element reach the last position by swapping elements

![Untitled](Bubble%20sort%20using%20recursion%2074a48d1b4b0e40b094af8e7d42926206/Untitled.png)

### Approach

Iteratively we take 2 loops

1. For rows
2. For colums

Recursively 

we will maintain 2 variables, rows and columns 

- Starts rows from the last element and keep decrementing them until it reaches 0
- Start columns from 0 and keep increasing them until col < rows

### Base case

When the rows reach 0

Backtrack or return to the last function call

### General case

Only if the cols are less than the rows

check if the element at cols is greater than the one ahead of it 

if yes, swap them

regardless of the swap, check for the next column

call the function by incrementing the cols pointer

If the cols are greater than the rows

go to the next row

call the function and decrement the rows pointer  

```java
public static void bubble(int[] arr, int r,int c){
	    if(r == 0) return;
	    
	    if(c<r){
	        if(arr[c] > arr[c+1]){
	            int temp = arr[c];
	            arr[c] = arr[c+1];
	            arr[c+1] = temp;
	        }
	        
	        bubble(arr,r,c+1);
	    } else{
	        bubble(arr,r-1,0);
	    }
	}
```