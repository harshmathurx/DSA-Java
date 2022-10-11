# Basics of recursion

Printing n numbers (descending)

```java
if(n == 0){
	        return;
	    }
	    
			//print n
	    System.out.println(n);

			// go to the next function call
	    fun(n-1);
	}
```

Print n numbers ascending 

```java
if(n == 0){
	        return;
	    }
	    
			// reach the last function call first
			fun(n-1);
	    System.out.println(n);
	}
```

Product of n numbers 

```java
public static int prod(int n){
	    if(n == 1){
	        return 1;
	    }
	    
	    return n * prod(n-1);
	}
```

Sum of n number 

```java
public static int sum(int n){
	    if(n == 1){
	        return 1;
	    }
	    
	    return n + sum(n-1);
	}
```

Sum of all digits of an integer 

```java
public static int sum(int n){
	    if(n%10 == n){
	        return n;
	    }
	    
	    return n%10 + sum(n/10);
	}
```

Product of all digits of an integer 

```java
public static int prod(int n){
	    if(n%10 == n){
	        return n;
	    }
	    
	    return n%10 * prod(n/10);
	}
```