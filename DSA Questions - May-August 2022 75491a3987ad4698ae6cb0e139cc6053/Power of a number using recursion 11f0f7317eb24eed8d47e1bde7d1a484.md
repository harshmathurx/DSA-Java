# Power of a number using recursion

```java
public static long pow(int x,int n){
	    if(n == 1){
	        return x * 1;
	    }
	    
	    return x * pow(x,n-1);
	}
```

### Optimal

```java
public static long Pow(int X, int N) {
		if(N == 0){
            return 1;
        }
        
        long temp = Pow(X,N/2); 
        
        if(N%2 == 1){
           return temp*temp*X;
        }
        return temp*temp;
	}
```