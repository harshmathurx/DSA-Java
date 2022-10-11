# Next Smaller to Right

```java
public static int[] smallerRight(int[] arr,int n){
	    int[] nse = new int[n];
	    Stack<Integer> st = new Stack<Integer>();
	    
			Arrays.fill(nse,-1);			

	    for(int i=n-1;i>=0;i--){
	        while(!st.isEmpty() && st.peek() > arr[i]){
	            st.pop();
	        }
	        if(!st.isEmpty()) {
	            nse[i] = st.peek();
	        }
	        st.push(arr[i]);
	    }
	    return nse;
	}
```