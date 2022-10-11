# Min Stack using O(1) Space

[Design a stack that supports getMin() in O(1) time and O(1) extra space - GeeksforGeeks](https://www.geeksforgeeks.org/design-a-stack-that-supports-getmin-in-o1-time-and-o1-extra-space/)

[Min Stack - LeetCode](https://leetcode.com/problems/min-stack/)

```java
		int min = Integer.MAX_VALUE;
    Stack<Integer> stack = new Stack<Integer>();
    public void push(int x) {
        // only push the old minimum value when the current 
        // minimum value changes after pushing the new value x
        if(x <= min){          
            stack.push(min);
            min=x;
        }
        stack.push(x);
    }
    public void pop() {
        // if pop operation could result in the changing of the current minimum value, 
        // pop twice and change the current minimum value to the last minimum value.
        if(stack.peek() == min){
					stack.pop();
					min=stack.peek();
					stack.pop();
				}
    }

    public int top() {
        return stack.peek();
    }

    public int getMin() {
        return min;
    }
```