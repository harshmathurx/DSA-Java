# Sum triangle array

Given an array of integers, print a sum triangle from it such that the first level has all array elements. From then, at each level number of elements is one less than the previous level and elements at the 
the level is the Sum of consecutive two elements in the previous level. **Example :**

```
Input : A = {1, 2, 3, 4, 5}
Output : [48]
         [20, 28]
         [8, 12, 16]
         [3, 5, 7, 9]
         [1, 2, 3, 4, 5]

Explanation :
Here,   [48]
        [20, 28] -->(20 + 28 = 48)
        [8, 12, 16] -->(8 + 12 = 20, 12 + 16 = 28)
        [3, 5, 7, 9] -->(3 + 5 = 8, 5 + 7 = 12, 7 + 9 = 16)
        [1, 2, 3, 4, 5] -->(1 + 2 = 3, 2 + 3 = 5, 3 + 4 = 7, 4 + 5 = 9)
```

### Approach

1. Base case: if the size of the array (reaches) is less than 1
2. Create a temporary array that contains the sums of the elements of the previous array
3. Add the values to the array iteratively 
4. Recursive function: Call the function for with the temporary array as a parameter 
5. Backtracking: Print the elements of the original array 

### Dry Run

For array : [ 1, 2, 3, 4, 5 ]

![Untitled](Sum%20triangle%20array%20a05cfd29ad3848c3b90e74b889e68be9/Untitled.png)

```java
public static void sumArr(int[] arr){
	    if(arr.length < 1){
	        return;
	    }
	    int[] temp = new int[arr.length-1];
	    for(int i=0;i<temp.length;i++){
	        temp[i] = arr[i] + arr[i+1];
	    }
	    sumArr(temp);
	    System.out.println(Arrays.toString(arr));
	}
```