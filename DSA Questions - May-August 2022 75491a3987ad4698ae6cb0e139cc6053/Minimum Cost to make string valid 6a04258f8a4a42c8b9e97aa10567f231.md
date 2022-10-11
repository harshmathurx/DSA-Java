# Minimum Cost to make string valid

[](https://www.codingninjas.com/codestudio/problems/minimum-cost-to-make-string-valid_1115770?leftPanelTab=0)

[https://youtu.be/BmZnJehDzyU?t=4426](https://youtu.be/BmZnJehDzyU?t=4426)

```java
	public static int findMinimumCost(String str) {
        if(str.length()%2 == 1){
            return -1;
        }
        
	    Stack<Character> st = new Stack<Character>();
        for(int i=0;i<str.length();i++){
            char ch = str.charAt(i);
            if(ch == '{'){
                st.push(ch);
            }
            else{
                  if(!st.isEmpty() && st.peek() == '{'){
                      st.pop();
                  }
                  else{
                      st.push(ch);
                  }
            }
        }
        
        int a=0,b=0;
        while(!st.isEmpty()){
            if(st.peek() =='{'){
                b++;
            } else {
                a++;
            }
            
            st.pop();
        }
        return (a+1)/2 + (b+1)/2;
    }
```