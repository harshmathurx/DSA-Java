# Next Greater Element

[https://www.youtube.com/watch?v=NXOOYYwpbg4&list=PL_z_8CaSLPWdeOezg68SKkeLN4-T_jNHd&index=2](https://www.youtube.com/watch?v=NXOOYYwpbg4&list=PL_z_8CaSLPWdeOezg68SKkeLN4-T_jNHd&index=2)

## Traverse in the array ulta

```java
public static long[] nextLargerElement(long[] arr, int n){ 
        long[] nge = new long[n];
        Stack<Long> st = new Stack<Long>();
        
        for(int i=n-1;i>=0;i--){
            while(!st.isEmpty() && st.peek() <= arr[i]){
                  st.pop();
            }
            if(!st.isEmpty()){
               nge[i] = st.peek();
            }
						else{
								nge[i] = -1;							
						}
            st.push(arr[i]);
        }
        
        return nge;
    }
```