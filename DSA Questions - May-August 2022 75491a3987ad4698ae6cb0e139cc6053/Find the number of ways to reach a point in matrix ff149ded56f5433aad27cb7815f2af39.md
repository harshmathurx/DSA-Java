# Find the number of ways to reach a point in matrix

![Untitled](Find%20the%20number%20of%20ways%20to%20reach%20a%20point%20in%20matrix%20ff149ded56f5433aad27cb7815f2af39/Untitled.png)

For example We need to reach the last row and last column 

We use the subsequence and subset method

## Approach

- Start from the (4,4) - example
- Keep reducing the row and column on each recursive call

### Base case

- When either column or row reaches 1
    - return 1
    - There is only one path left when you reach the edge of the matrix, either right or down

![Untitled](Find%20the%20number%20of%20ways%20to%20reach%20a%20point%20in%20matrix%20ff149ded56f5433aad27cb7815f2af39/Untitled%201.png)

```java
public static int countWays(int r,int c){
	    if(r == 1 || c== 1){
	        return 1;
	    }
	    
	    int right = countWays(r-1,c);
	    int left = countWays(r,c-1);
	    
	    return right + left;
	}
```