# Return all substrings of a string

![Untitled](Return%20all%20substrings%20of%20a%20string%2038f972a30a134fc290863a2675b4e5be/Untitled.png)

```java
public static void substr(String str,String ans){
	    if(str.isEmpty()){
	        System.out.println(ans);
	        return;
	    }
	    
	    char ch = str.charAt(0);
	    
	    substr(str.substring(1),ans+ch);
	    substr(str.substring(1),ans);
	}
```