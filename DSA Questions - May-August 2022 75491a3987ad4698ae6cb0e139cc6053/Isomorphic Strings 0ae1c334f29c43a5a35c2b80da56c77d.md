# Isomorphic Strings

[Isomorphic Strings - LeetCode](https://leetcode.com/problems/isomorphic-strings)

[https://www.youtube.com/watch?v=TsTuKNA2K2k](https://www.youtube.com/watch?v=TsTuKNA2K2k)

```java
	public boolean isIsomorphic(String s1, String s2) {
        if(s1.length() != s2.length()){
            return false;
        }
        int[] m = new int[512];
        for (int i = 0; i < s1.length(); i++) {
            if (m[s1.charAt(i)] != m[s2.charAt(i)+256]){
							return false;
						}
						else {
	            m[s2.charAt(i)+256] = i+1;
							m[s1.charAt(i)] = i+1;
		        }
				}
        return true;
    }
```