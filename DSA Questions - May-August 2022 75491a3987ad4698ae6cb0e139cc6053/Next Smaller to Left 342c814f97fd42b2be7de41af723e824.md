# Next Smaller to Left

[Nearest Smaller Element - InterviewBit](https://www.interviewbit.com/problems/nearest-smaller-element/)

```java
public int[] prevSmaller(int[] arr,int n) {
        int[] nse = new int[n];
        Stack<Integer> st = new Stack<Integer>();
        
				Arrays.fill(nse,-1);
				
        for(int i=0;i<n;i++){
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