# Best time to buy and sell stocks

[Best Time to Buy and Sell Stock - LeetCode](https://leetcode.com/problems/best-time-to-buy-and-sell-stock/)

# Approach

### Brute-force

- Traverse through the array using i
- traverse from i+1 to end using j
- if a[j] > a[i]
- set max of both as profit

### Better Approach

- Maintain 2 variables, minority, maxPro
- Traverse through the array
- set minPrice as the minimum of minority and the current value
- set maxPro as the maximum of maxPro and the difference between the values of i and minPrice

```java
public int maxProfit(int [] prices){
	int minPrice = Integer.MAX_VALUE;
	int maxPro = 0;
	for(int i=0;i<prices.length;i++){
		minPrice = Math.min(minPrice,a[i]);
		maxPro = Math.max(maxPro,(a[i] - minPrice));
	}
	return maxPro;
}
```

[https://www.youtube.com/watch?v=eMSfBgbiEjk&list=PLgUwDviBIf0rPG3Ictpu74YWBQ1CaBkm2&index=11](https://www.youtube.com/watch?v=eMSfBgbiEjk&list=PLgUwDviBIf0rPG3Ictpu74YWBQ1CaBkm2&index=11)