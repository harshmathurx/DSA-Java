# Stock Span Problem

[https://www.youtube.com/watch?v=-IFmgue8sF0](https://www.youtube.com/watch?v=-IFmgue8sF0)

## Idea

- The problem is very similar to the

[Next Greater to Left](Next%20Greater%20to%20Left%20d09e93749012475a9ef13361bc5296a5.md)

- The only change is that we need to check the indexes as well as the values of the array
- We store the indexes in the stack
- Then we compare the current element to the top of the stack as we normally do

## Approach

- Add the 0th index of the stack and the result array before the loop (this will never change)
- `st.push(0); res[0] = 1;`
- Iterate from 1 to n
    - if the price at the current index is greater than that of the index at the top of the stack
        - pop
    - If the stack is empty
        - add i + 1 to the result array
        - This is because it is the greatest price until now
    - Else (Stack is not empty)
        - add i - stack.peek() to the result array
        - This is the no. of consecutive smaller elementyou than the current element
    - Push `i` to the stack (this will always happen)

```java
public static int[] calculateSpan(int prices[], int n){
        int[] res = new int[n];
        Stack<Integer> st = new Stack<Integer>();
        
        //0th index is always the same 
        st.push(0);
        res[0] = 1;
        
        //iterate in the array and check
        for(int i=1;i<n;i++){
            while(!st.isEmpty() && (prices[st.peek()]  <= prices[i])){
                st.pop();
            }
            
            if(st.isEmpty()){
                res[i] = i+1;
            } else{
                res[i] = i-st.peek();
            }
            st.push(i);
        }
        return res;
   
}
```