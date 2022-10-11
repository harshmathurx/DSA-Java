# Valid palindrome

[Valid Palindrome - LeetCode](https://leetcode.com/problems/valid-palindrome)

## Approach

- Use 2 pointer approach
- start and end pointer
- normal palindrome checking method but something different
- for every character, check if it is a number or a character
    - if not, move to the next character

```java
public boolean isPalindrome(String s) {
        int left = 0;
        int right = s.length() - 1;
        while (left < right) {
            if (!Character.isLetterOrDigit(s.charAt(left))) {
                left++;
                continue;
            }
            if (!Character.isLetterOrDigit(s.charAt(right))) {
                right--;
                continue;
            }
            if (Character.toLowerCase(s.charAt(left)) != Character.toLowerCase(s.charAt(right))) {
                return false;
            }
            left++;
            right--;
        }
        return true;
    }
```