# Happy Number

[Happy Number - LeetCode](https://leetcode.com/problems/happy-number/)

Write an algorithm to determine if a number `n` is happy.

A **happy number** is a number defined by the following process:

- Starting with any positive integer, replace the number by the sum of the squares of its digits.
- Repeat the process until the number equals 1 (where it will stay), or it **loops endlessly in a cycle** which does not include 1.
- Those numbers for which this process **ends in 1** are happy.

Return `true` *if* `n` *is a happy number, and* `false` *if not*.

## Approach

- first, we find the square of the number
- then we find the square of each number and add it to the make the next number
- Now, we use the fast and slow pointer method to find whether they will meet at a certain point again or not
- when the slow pointer reaches 1
    - return true
- otherwise return false

```java
public boolean isHappy(int n) {
        int slow = n;
        int fast = n;
        
        do{
            slow = findSquare(slow);
            fast = findSquare(findSquare(fast));
        } while(fast != slow);
        
        if(slow == 1){
            return true;
        }
        return false;
    }
    
    public int findSquare(int n){
        int ans = 0;
        while(n > 0){
            int rem = n % 10;
            ans += rem * rem;
            n = n/10;
        }
        return ans;
    }
```