# Check if an array is sorted using recursion

## Approach

- Use an index variable to pass in the function to jump through the elements in the array
- Check if the current element is smaller than the next element and the same for the rest of the calls
- Base condition - if you have reached the last element of the array
    - return true

 

```java
public static boolean sorted(int[] arr, int index){
        if(arr.length - 1 == index){
            return true;
        }
        
        return arr[index] < arr[index + 1] && sorted(arr,index + 1);
    }
```