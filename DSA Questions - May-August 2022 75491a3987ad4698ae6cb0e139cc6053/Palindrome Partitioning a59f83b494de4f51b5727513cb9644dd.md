# Palindrome Partitioning

[Palindrome Partitioning - LeetCode](https://leetcode.com/problems/palindrome-partitioning)

## Base case

- If the length of the string is 0
    - add an empty arraylist to the result list

Keep a temp array handy to add temporary strings 

Only add strings in the result array at the base case 

Iterate over the string

recursively call the function with the a new substring 

```java
public static List<List<String>> partition(String s) {
        List <List<String>> res = new ArrayList <> ();
        List <String> path = new ArrayList <> ();
        func(0, s, path, res);
        return res;
    }

    static void func(int index, String s, List < String > path, List < List < String >> res) {
        if (index == s.length()) {
            res.add(new ArrayList < > (path));
            return;
        }
        for (int i = index; i < s.length(); ++i) {
            if (isPalindrome(s, index, i)) {
                path.add(s.substring(index, i + 1));
                func(i + 1, s, path, res);
                path.remove(path.size() - 1);
            }
        }
    }

    static boolean isPalindrome(String s, int start, int end) {
        while (start <= end) {
            if (s.charAt(start++) != s.charAt(end--))
                return false;
        }
        return true;
    }
```