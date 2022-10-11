# MyAtoi (String to integer)

[String to Integer (atoi) - LeetCode](https://leetcode.com/problems/string-to-integer-atoi)

# Approach

- Keep a variable called FLAG to check if the number is positive or negative
- default value of FLAG is +
- Check if the first char of the string is **-** or **+**

- Loop through the string
    - If the char is a number i.e. ≥0 & ≤9
    - construct the number

```jsx
public int myAtoi(String str) {
        str = str.trim();
        if (str == null || str.length() < 1) return 0;
        char flag = '+';

        int i = 0;
        if (str.charAt(0) == '-') {
            flag = '-';
            i++;
        } else if (str.charAt(0) == '+') {
            i++;
        }
        // use double to store result
        double result = 0;

        while (str.length() > i && str.charAt(i) >= '0' && str.charAt(i) <= '9') {
            result = result * 10 + (str.charAt(i) - '0');
            i++;
        }

        if (flag == '-')
            result = -result;

        // handle max and min
        if (result > Integer.MAX_VALUE)
            return Integer.MAX_VALUE;

        if (result < Integer.MIN_VALUE)
            return Integer.MIN_VALUE;

        return (int) result;
    }
```

# Edge cases

- Trim the string to ignore whitespaces
- Check if the string’s length is greater than 0

- If the value of the result is greater than what the integer can handle
    - return max value of integer
- If the value of the result is lesser than what the integer can handle
    - return min value of integer