# Sort characters by frequency

[Sort Characters By Frequency - LeetCode](https://leetcode.com/problems/sort-characters-by-frequency/)

# Brute Force

- The ASCII values of characters are from 0 to 255
- We create an integer array to store the frequency of each character
- After getting the frequency
- We sort the array in descending order
- Build the string by traversing in the array

```java
public String frequencySort(String s) {
        int map[] = new int[256];
        int len = s.length();
        Character str[] = new Character[len];
        
        for(int idx = 0;idx<len;idx++){
            char ch = s.charAt(idx);
            str[idx] = ch;
            map[ch]++;
        }
        
        Arrays.sort(str,(charA,charB)->
                    (map[charA]==map[charB])?             
                    Integer.compare(charA,charB):Integer.compare(map[charB],map[charA]));
        
        StringBuilder ansStr = new StringBuilder();
        for(int idx = 0;idx<len;idx++){
            ansStr.append(str[idx]);
        }
        
        return ansStr.toString();
    }
```