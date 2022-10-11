# Reverse a string using Stack

```java
public static String reverse(String str){
	    char[] reverse = new char[str.length()];
	    Stack<Character> stack = new Stack<Character>();
	    for(int i=0;i<str.length();i++){
	        stack.push(str.charAt(i));
	    }
	    
	    int i=0;
	    while(!stack.isEmpty()){
	        reverse[i] = stack.peek();
	        stack.pop();
	        i++;
	    }
	    return new String(reverse);
	}
```