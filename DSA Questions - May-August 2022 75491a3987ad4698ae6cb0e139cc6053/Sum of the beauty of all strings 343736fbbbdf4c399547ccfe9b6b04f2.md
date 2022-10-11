# Sum of the beauty of all strings

[Sum of Beauty of All Substrings - LeetCode](https://leetcode.com/problems/sum-of-beauty-of-all-substrings/)

## Brute Force

- Generate all substrings
- Calculate frequencies
- Return max

## Optimized Approach

- We create a frequencies array of 26 integers
- Since the string only contains lowercase characters, we only need 26 frequencies

```java
public int beautySum(String s) {
        int result = 0;
        int[] frequencies = new int[26];
        for(int i=0;i<s.length();i++) {
            
            // any lowercase alphabet - 'a' gives us an integer between 0 - 25
            // 'a' - 'a' = 0 // 'b' - 'a' = 1 and so on
            frequencies[s.charAt(i)-'a']++;
            
            result += helper(frequencies);
        }
        
        if(s.length()>1) result += beautySum(s.substring(1));
        return result;
    }
    private int helper(int[] frequencies) {
        int max =0, min =Integer.MAX_VALUE;
        for(int i=0;i<26;i++) {
            max = Math.max(max, frequencies[i]);
            if(frequencies[i]!=0) min = Math.min(min, frequencies[i]);
        }
        return max - min;
    }
```