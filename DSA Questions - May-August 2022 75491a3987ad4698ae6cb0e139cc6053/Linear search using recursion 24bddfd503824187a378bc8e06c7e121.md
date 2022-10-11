# Linear search using recursion

```java
public static int search(int[] arr, int x, int index){
        if(arr[index] == x){
            return index + 1;
        }
        
        if(index == arr.length - 1) return -1;
        
        return search(arr,x,index + 1);
    }
```