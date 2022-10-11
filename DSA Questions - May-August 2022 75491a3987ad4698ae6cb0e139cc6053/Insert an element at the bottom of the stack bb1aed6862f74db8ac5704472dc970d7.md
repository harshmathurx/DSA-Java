# Insert an element at the bottom of the stack

```java
public static Stack<Integer> pushAtBottom(Stack <Integer> myStack, int x) 
  {
      solve(myStack,x);
      return myStack;
  }
    
  public static void solve(Stack<Integer> stack,int x){
      if(stack.isEmpty()){
          stack.push(x);
          return;
      }
      
      int n = stack.peek();
      stack.pop();
      
      solve(stack,x);
      
      stack.push(n);
  }
```