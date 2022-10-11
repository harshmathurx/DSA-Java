# Min Stack Using Extra Space

[Min Stack - LeetCode](https://leetcode.com/problems/min-stack)

[https://www.youtube.com/watch?v=asf9P2Rcopo&list=PL_z_8CaSLPWdeOezg68SKkeLN4-T_jNHd&index=11](https://www.youtube.com/watch?v=asf9P2Rcopo&list=PL_z_8CaSLPWdeOezg68SKkeLN4-T_jNHd&index=11)

## Idea

The idea is to keep the minimum element of the stack at the top of the support stack  

When you push, check if the top element of the support stack has an element greater than the element 

If yes, push in the support stack as well 

While popping an element

If the element popped from the stack is equal to the one at the top of the support stack

Pop it from the support stack as well 

  

```java
		public MinStack() {
        s = new Stack<Integer>();
        ss = new Stack<Integer>();
    }
    
    public void push(int val) {
        s.push(val);
        if(ss.isEmpty() || ss.peek() >= val){
            ss.push(val);
        }
    }
    
    public void pop() {
        int x = s.pop();
        if(x == ss.peek()){
            ss.pop();
        }
    }
    
    public int top() {
        return s.peek();
    }
    
    public int getMin() {
        if(ss.isEmpty()){
            return -1;
        }
        return ss.peek();
    }
```