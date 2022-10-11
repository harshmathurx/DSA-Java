# Move all the Xs at the end of the String

## Explanation

- we extract the first char of the string and call the recursive function
- this way, we reach the last char of the string
- then we check if the char is x
    - if yes, add it to the end of the string and return
    - otherwise add it to the front of the string, like it was before, and return

```java
public static String move(String s){
	    if(s.length() == 0){
	        return s;
	    }
        
        char ch = s.charAt(0);
        String ans = move(s.substring(1));
        if(ch == 'x'){
            return ans+ch;
        }
        
        return ch+ans;
	}
```