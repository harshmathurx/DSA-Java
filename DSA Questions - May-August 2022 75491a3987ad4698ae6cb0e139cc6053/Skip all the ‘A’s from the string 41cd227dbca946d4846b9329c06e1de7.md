# Skip all the ‘A’s from the string

The idea is to skip all the As from a string and return a string 

```java
public static String skipA(String str){
	    if(str.isEmpty()){
	        return "";
	    }
	    
	    char ch = str.charAt(0);
	    if(ch == 'a'){
	        return skipA(str.substring(1));
	    }
	    else{
	        return ch + skipA(str.substring(1));
	    }
	}
```