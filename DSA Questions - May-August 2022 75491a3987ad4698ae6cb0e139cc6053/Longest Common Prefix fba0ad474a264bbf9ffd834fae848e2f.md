# Longest Common Prefix

[Longest Common Prefix - LeetCode](https://leetcode.com/problems/longest-common-prefix/)

# Approach

- To check the prefixes of the strings, we do not need to loop through all the strings
- We can also check the same only using the first and the last string

(because the prefix will be the same in all)

- Sort the input array
- Use a string builder
- Create a char array out of the

```java
public String longestCommonPrefix(String[] strs) {
        StringBuilder sb = new StringBuilder();
        Arrays.sort(strs);
        
        char[] first = strs[0].toCharArray();
        char[] last = strs[strs.length-1].toCharArray();
        
        for(int i=0;i<first.length && i<last.length;i++){
            if(first[i] == last[i]){
                sb.append(last[i]);
            }
            else{
                return sb.toString();
            }
        }
        return sb.toString();
    }
```