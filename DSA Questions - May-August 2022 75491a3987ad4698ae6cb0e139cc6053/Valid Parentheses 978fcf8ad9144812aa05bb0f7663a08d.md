# Valid Parentheses

[Valid Parentheses - LeetCode](https://leetcode.com/problems/valid-parentheses/)

```java
public boolean isValid(String s) {
        Stack<Character> st = new Stack<>();
        
        for(int i=0;i<s.length();i++){
            //opening parantheses
            if(s.charAt(i)=='('){
                st.push(s.charAt(i));
            }else if(s.charAt(i)=='{'){
                st.push(s.charAt(i));
            }else if(s.charAt(i)=='['){
                st.push(s.charAt(i));
            }
            
            if(st.isEmpty()) return false;
            
            //closing parantheses
            if(s.charAt(i)=='}' && st.pop()!='{'){
                return false;
            }else if(s.charAt(i)==')' && st.pop()!='('){
                return false;
            }else if(s.charAt(i)==']' && st.pop()!='['){
                return false;
            }
        }
        
        
        if(!st.isEmpty()){
                return false;
            }
        return true;
    }
```