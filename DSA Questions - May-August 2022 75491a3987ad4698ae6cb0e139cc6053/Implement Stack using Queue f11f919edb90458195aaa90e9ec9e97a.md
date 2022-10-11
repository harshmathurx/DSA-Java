# Implement Stack using Queue

[Implement Stack using Queues - LeetCode](https://leetcode.com/problems/implement-stack-using-queues/submissions/)

## Approach

- We normally need to perform all the operations that we perform on a queue
- The only function that changes in order to make it work as a stack is `push()`

### Push function

- We add the element in the queue
- We then need to reverse the order of the elements of the stack
- So we loop from the first element to the second last element
    - remove the element from the queue (first)
    - Add it to the queue (becomes last)
- Now the queue is flipped, hence it is a stack

[https://youtu.be/jDZQKzEtbYQ?t=432](https://youtu.be/jDZQKzEtbYQ?t=432)

```java
class MyStack {
    Queue<Integer> q;
    
    public MyStack() {
        q = new LinkedList<Integer>();
    }
    
    public void push(int x) {
        q.add(x);
        for(int i=0;i<q.size() - 1;i++){
            q.add(q.remove());
        }
    }
    
    public int pop() {
        return q.remove();
    }
    
    public int top() {
        return q.peek();
    }
    
    public boolean empty() {
        return q.size() == 0;
    }
}
```