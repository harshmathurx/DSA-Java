# binary search using recursion

```java
public static int search(int[] arr,int x,int l,int r){
        if(l>r){
            return -1;
        }
        
        int m = l + (r-l)/2;
        
        if(arr[m] == x){
            return m+1;
        }
        
        if(r>=l){
            if(arr[m] > x){
                return search(arr,x,l,m-1);
            }
            if(arr[m] < x){
                return search(arr,x,m+1,r);
            }
        }
        
        return -1;
    }
```