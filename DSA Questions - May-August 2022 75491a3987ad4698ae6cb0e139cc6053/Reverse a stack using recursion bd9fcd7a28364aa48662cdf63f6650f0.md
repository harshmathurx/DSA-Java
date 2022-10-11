# Reverse a stack using recursion

```java
	public static void reverseStack(Stack<Integer> stack) {
			if(stack.isEmpty()) return;
	        
	        int n = stack.peek();
	        stack.pop();
	        
	        reverseStack(stack);        
	        insertBottom(stack,n);
		}
    
    public static void insertBottom(Stack<Integer> stack,int x){
      if(stack.isEmpty()){
          stack.push(x);
          return;
      }
      
      int n = stack.peek();
      stack.pop();
      
      insertBottom(stack,x);
      
      stack.push(n);
  }
```