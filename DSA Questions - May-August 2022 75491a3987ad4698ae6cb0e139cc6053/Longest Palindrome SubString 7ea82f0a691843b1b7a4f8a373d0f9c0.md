# Longest Palindrome SubString

[Longest Palindromic Substring - LeetCode](https://leetcode.com/problems/longest-palindromic-substring/)

# Brute Force

- Generate all possible substrings of the string
- Store them in a list
- Check the ones which are palindrome
- return the one with the max length

# Optimized Solution

[https://www.youtube.com/watch?v=y2BD4MJqV20](https://www.youtube.com/watch?v=y2BD4MJqV20)

```java
	public String longestPalindrome(String s) {
        if(s == null || s.length() < 1){
            return "";
        }
        
        int start = 0;
        int end = 0;
        
        for(int i=0;i<s.length();i++){
            int len1 = palindromeSearch(s,i,i);
            int len2 = palindromeSearch(s,i,i+1);
            int len = Math.max(len1,len2);
            
            if(len > end - start){
                start = i - ((len-1)/2);
                end = i + (len/2);
            }
        }
        return s.substring(start,end+1);
    }
    
    public int palindromeSearch(String s,int left,int right){
        if(s == null || left>right){
            return 0;
        }
        
        while(left >= 0 && right < s.length() && s.charAt(left) == s.charAt(right)){
            left--;
            right++;
        }
        
        return right - left - 1;
    }
```

# Tricky Parts of the code

```java
						if(len > end - start){
                start = i - ((len-1)/2);
                end = i + (len/2);
            }
```

When we find a new max substring 

We reset the start and end values to that particular substring 

### In the function `palindromeSearch`

```java
 return right - left - 1;
```

We add the -1 for a reason 

While checking for the palindrome 

We move left and right one last time forward before we break the loop 

(Therefore we reach the breaking condition)

That’s why we decrease the result length by 1