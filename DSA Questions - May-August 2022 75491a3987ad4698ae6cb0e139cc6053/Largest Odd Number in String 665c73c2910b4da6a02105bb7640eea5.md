# Largest Odd Number in String

[Largest Odd Number in String - LeetCode](https://leetcode.com/problems/largest-odd-number-in-string)

# How to identify an odd number?

when the last digit is odd

## So the approach

We traverse from the back 

If we find a character who is odd

that makes the entire number before it - odd

We return all the digits before it as an odd number 

Otherwise, we return the empty string

 

```java
public String largestOddNumber(String num) {
        for(int i=num.length() - 1; i>=0; i--)
		    if(num.charAt(i) % 2 != 0) return num.substring(0, i + 1);
	    return "";
    }
```