# Next Greatest Element - II

[Next Greater Element II - LeetCode](https://leetcode.com/problems/next-greater-element-ii/)

[https://www.youtube.com/watch?v=NXOOYYwpbg4&list=PL_z_8CaSLPWdeOezg68SKkeLN4-T_jNHd&index=2](https://www.youtube.com/watch?v=NXOOYYwpbg4&list=PL_z_8CaSLPWdeOezg68SKkeLN4-T_jNHd&index=2)

## Approach

- We use a stack to store the temp variables
- We use an array nge to store the next greater elements
- We iterate from the back of the array to the front
    - If the stack has elements less than or equal to arr[i]
        - we pop them
    - if i is less than n i.e. it is not a circular array yet
        - if the stack is not empty
            - nge[i] = the element at the top of the stack
        - else (if the stack is empty)
            - you have the greatest element
            - nge[i] = -1
    - push the element at i in the stack
- Return nge

## The catch

- Since it is a circular array
- We use i%n to access the elements instead of i

```java
public int[] nextGreaterElements(int[] nums) {
        int n = nums.length;
        int[] nge = new int[n];
        Stack<Integer> stack = new Stack<Integer>();
        for(int i=2*n-1;i>=0;i--){
            while(!stack.isEmpty() && stack.peek() <= nums[i%n]){
                stack.pop();
            }
            
            if(i<n){
                if (!stack.isEmpty()){
                    nge[i] = stack.peek();   
                }
                else{
                    nge[i] = -1;   
                }
            }
            
            stack.push(nums[i%n]);
        }
        return nge;
    }
```