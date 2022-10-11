# Replace pi from string

[Recursive program to replace all occurrences of pi with 3.14 in a given string - GeeksforGeeks](https://www.geeksforgeeks.org/recursive-program-to-replace-all-occurrences-of-pi-with-3-14-in-a-given-string/)

```java
public static String pi(String s){
	    if(s.length() <= 1){
	        return s;
	    }
	    
	    if(s.charAt(0) == 'p' && s.charAt(1) == 'i'&& s.length() >= 2){
	        return "3.14" + pi(s.substring(2,s.length()));
	    }
	   return s.charAt(0) + pi(s.substring(1,s.length()));
	}
```