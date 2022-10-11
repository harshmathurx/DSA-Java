# Delete Middle Element from Stack

## Approach

- Keep removing 1 element from the stack for every recursive call
- When you reach the mid index
    - remove one more element
    - return

```java
		public static void deleteMiddle(Stack<Integer> stack, int N) {
			delete(stack,0,N-1);
		}
    
    public static void delete(Stack<Integer> stack, int i,int N){
        if(i == N/2){
            stack.pop();
            return;
        }
        
        int n = stack.peek();
        stack.pop();
        
        delete(stack,i+1,N);
        
        stack.push(n);
    }
```