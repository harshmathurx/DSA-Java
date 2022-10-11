# Skip string with a certain word

```java
public static String skipA(String str,String word){
	    if(str.isEmpty()){
	        return "";
	    }
	    
	    if(str.startsWith(word)){
	        return skipA(str.substring(word.length()),word);
	    }
	    else{
	        return str.charAt(0) + skipA(str.substring(1),word);
	    }
	}
```