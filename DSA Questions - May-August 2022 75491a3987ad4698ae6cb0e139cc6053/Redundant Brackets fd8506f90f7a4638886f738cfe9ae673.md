# Redundant Brackets

[](https://www.codingninjas.com/codestudio/problems/redundant-brackets_975473)

## Idea

- A bracket pair is redundant if there is no arithmetic operator between 2 closing brackets

## Approach

- We keep a stack aside to push and pop characters in the string
- Loop through the characters of the string

2 Cases 

- If you find an opening bracket or any arithmetic operator
    - Push it into the stack
- Else
    - if the char is a closing bracket
        - keep a Boolean variable handy to check the redundancy
        - now check the elements of the stack
            - loop until you get an opening bracket in the stack
                - check every element on the top of the stack
                    - if there is an operator at the top of the stack
                        - mark it as redundant
                        - pop the element
            - When the loop is terminated
            - Check if the redundant boolean
                - if true
                    - return true
            - pop the element
- After the for loop terminates
- return false

## TL;DR

- If there is an opening bracket or operator, push it into the stack
- Ignore the variables
- if there is a closing bracket, check the elements in the stack
- If you find an operator before you find an opening bracket
    - return false
- If there is an opening bracket before the operator
    - return true
- If the loops terminate
    - return false

```java
public static boolean findRedundantBrackets(String s) 
    {
        Stack<Character> stack = new Stack<Character>();
        for(int i=0;i<s.length();i++){
            char ch = s.charAt(i);
            if(ch == '(' ||  ch == '+' || ch == '-' || ch == '*' || ch == '/' || ch == '%'){
                stack.push(ch);
            }
            else{
                if(ch == ')'){
                    boolean isRedundant = true;
                    while(stack.peek() != '('){
                        char top = stack.peek();
                        if(top == '+' || top == '-' || top == '*' || top == '/' || top == '%'){
                            isRedundant = false;
                        }
                        stack.pop();
                    }
                    if(isRedundant){
                        return true;
                    }
                    stack.pop();
                }   
            }
        }
        return false;
    }
```