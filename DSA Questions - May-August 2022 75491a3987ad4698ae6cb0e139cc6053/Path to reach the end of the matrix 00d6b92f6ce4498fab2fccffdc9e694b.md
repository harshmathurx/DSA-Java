# Path to reach the end of the matrix

```java
public static void path(String p,int r,int c){
	    if(r == 1 && c == 1){
	        System.out.println(p);
	        return;
	    }
	    if(r > 1) path(p+'R',r-1,c);
	    if(c > 1) path(p+'D',r,c-1);
	}
```