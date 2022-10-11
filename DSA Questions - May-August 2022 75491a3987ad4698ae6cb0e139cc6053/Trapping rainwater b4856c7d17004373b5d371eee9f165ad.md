# Trapping rainwater

[Trapping Rain Water - LeetCode](https://leetcode.com/problems/trapping-rain-water/)

## Approach

- We need 2 arrays left and right
- Each array represents the maximum height to the index’s left or right

![Untitled](Trapping%20rainwater%20b4856c7d17004373b5d371eee9f165ad/Untitled.png)

- Then we iterate from the first index to the last index
- calculating the water that can be stored at each index
- formula for calculation
    
    ```java
    ans[i] = (Math.min(left[i],right[i]) - a[i]);
    ```
    
- return the answer array

**NOTE: we do not calculate the water for the 0th index because it does not store any water (the left has no height to it so the water overflows)**

```java
public int trap(int[] a) {
        int n = a.length;
        int[] left = new int[n];
        int[] right = new int [n];
        
        left[0] = a[0];
        for(int i=1;i<n;i++){
            left[i] = Math.max(left[i-1],a[i]);
        }
        
        right[n-1] = a[n-1];
        for(int i=n-2;i>=0;i--){
            right[i] = Math.max(right[i+1],a[i]);
        }
        
        int ans = 0;
        for(int i=0;i<n;i++){
            ans += Math.min(left[i],right[i]) - a[i];
        }
        
        return ans;
    }
```