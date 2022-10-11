# Implement Queue using stack

[Implement Queue using Stacks - LeetCode](https://leetcode.com/problems/implement-queue-using-stacks)

We need 2 queues - Input, and Output

### Push function

- Push the element into the input array

### Pop Function

- We need to remove the first element of the output stack
- But if the output stack is empty
    - We copy all the elements from the input stack to the output stack in the reverse order
    - remove the first element of the output stack

```java
class MyQueue {
    Stack<Integer> input;
    Stack<Integer> output;
    
    public MyQueue() {
        input = new Stack<Integer>();
        output = new Stack<Integer>();
    }
    
    public void push(int x) {
        input.push(x);
    }
    
    public int pop() {
        if(output.empty()){
            while(!input.empty()){
                output.push(input.peek());
                input.pop();
            }
        }
        
        int x = output.peek();
        output.pop();
        return x;
    }
    
    public int peek() {
        if (output.empty())
            while (input.empty() == false) {
                output.push(input.peek());
                input.pop();
            }
        return output.peek();
    }
    
    public boolean empty() {
        return (output.size() + input.size()) == 0;
    }
}
```