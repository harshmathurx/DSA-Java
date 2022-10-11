# Next Greater to Left

[https://www.youtube.com/watch?v=T5s96ynzArg&list=PL_z_8CaSLPWdeOezg68SKkeLN4-T_jNHd&index=3](https://www.youtube.com/watch?v=T5s96ynzArg&list=PL_z_8CaSLPWdeOezg68SKkeLN4-T_jNHd&index=3)

```java
public static int[] greaterRight(int[] arr,int n){
	    int[] nge = new int[n];
	    Stack<Integer> st = new Stack<Integer>();
	   
			Arrays.fill(nge,-1);	    

	    for(int i=0;i<n;i++){
	        if(st.isEmpty()){
	            nge[i] = -1;
	            st.push(arr[i]);
	        } else {
	           while(!st.isEmpty() && st.peek() < arr[i]){
	            st.pop();
	            }
	            if(!st.isEmpty()){
    	            nge[i] = st.peek();
	            }
	            st.push(arr[i]);
	        }
	    }
	    return nge;
	}
```