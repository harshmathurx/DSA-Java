# Nth Root of an integer (1)

[](https://www.codingninjas.com/codestudio/problems/1062679?topList=striver-sde-sheet-problems&utm_source=striver&utm_medium=website)

## Approach

- The idea is to find a double m such that int n * double m  = long m
- Since it is a double, we need to find the decimal places up to 5 decimals
- We can't keep iterating and increasing the value of n by 1 or even 0.00001

We use Binary Search 

- We start with checking if the number lies in which of the 2 ranges
    - low to mid // 1 to ((high + low)/ 2)
    - mid to high
- We keep reducing the search space by half, until we find the answer
- We just need to make sure that we don't look beyond 5 decimal points, so the iteration condition is
- while (high - low) > 1e-6

```java
		public static double findNthRootOfM(int n, long m) {
	    	double low = 1;
        double high = m;
        double eps = 1e-6; 
        
        while((high - low) > eps) {
            double mid = (low + high) / 2.0; 
            if(multiply(mid, n) < m) {
                low = mid; 
            }
            else {
                high = mid; 
            }
        }
        return low;
    }
    
    private static double multiply(double number, int n) {
        double ans = 1.0;
        for(int i = 1;i<=n;i++) {
            ans = ans * number;
        }
        return ans; 
    }
```