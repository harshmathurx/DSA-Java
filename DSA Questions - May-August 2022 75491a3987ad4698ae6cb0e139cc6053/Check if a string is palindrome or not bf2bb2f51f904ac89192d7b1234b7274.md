# Check if a string is palindrome or not

```java
public static boolean isPal(String str, int s,int e){
	    if(s>=e){
	        return true;
	    }
	    
	    if(str.charAt(s) != str.charAt(e)){
	        return false;
	    }
	    
	    return isPal(str,s+1,e-1);
	}
```