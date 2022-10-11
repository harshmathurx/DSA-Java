# Remove outermost parenthesis

[Remove Outermost Parentheses - LeetCode](https://leetcode.com/problems/remove-outermost-parentheses/)

# Approach

- Keep a count of 3 things
    - opened - no. of opening braced
    - closed - no. of closing braces
    - start - closest opening brace to i
        
        The start pointer changes whenever open == close
        
        It switched the next pair of outermost parenthesis 
        

```java
public String removeOuterParentheses(String S) {
        StringBuilder sb = new StringBuilder();
        int open=0, close=0, start=0;
        for(int i=0; i<S.length(); i++) {
            if(S.charAt(i) == '(') {
                open++;
            } else if(S.charAt(i) == ')') {
                close++;
            }
            
						// add only the inner parenthesis to the sb
						// move to the next opening brace outside this pair 
            if(open==close) {
                sb.append(S.substring(start+1, i));
                start=i+1;
            }
        }
        return sb.toString();
    }
```