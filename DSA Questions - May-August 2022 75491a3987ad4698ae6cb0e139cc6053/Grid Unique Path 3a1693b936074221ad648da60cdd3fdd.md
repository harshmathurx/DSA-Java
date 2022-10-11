# Grid Unique Path

[Unique Paths - LeetCode](https://leetcode.com/problems/unique-paths)

## Brute Force

- Start at 0,0
- Set base cases
    - if reached n-1,m-1
        - return 1
    - if i exceeds n or if j exceeds m
        - return 0
    - else
        - backtrack
        - return count(i+1,j) + count(i,j+1)

```java
public int uniquePaths(int m, int n) {
        int ans = countPaths(0,0,m,n); 
        return ans;
    }
    
    public int countPaths (int i, int j,int m, int n){
        if(i==(n-1) && j==(m-1)){
            return 1;
        }
        if(i>=n || j>=m){
            return 0;
        } else{ 
            return (countPaths(i+1,j,m,n) + countPaths(i,j+1,m,n));
        }
    }
```