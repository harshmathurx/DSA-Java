# Pascal’s Triangle

[Pascal's Triangle - LeetCode](https://leetcode.com/problems/pascals-triangle/)

![Untitled](Pascal%E2%80%99s%20Triangle%208f18b44036df4e6cbf364e736cf839f4/Untitled.png)

### Approach

- The first and last element of the row will always be 1
- The nth element of the row will be the sum of the n and n-1th element of the last row

```java
public List<List<Integer>> generate(int numRows) {
        List<List<Integer>> res = new ArrayList<List<Integer>>();
        for(int i=1;i<=numRows;i++){
            List<Integer> row = new ArrayList<Integer>();
            for(int j=0;j<i;j++){
                if(j == 0 || j == i-1){
                    row.add(1);
                }
                else{
	                row.add(res.get(i-2).get(j) + res.get(i-2).get(j-1));   
                }
            }
            res.add(row);
        }
        return res;
    }
```