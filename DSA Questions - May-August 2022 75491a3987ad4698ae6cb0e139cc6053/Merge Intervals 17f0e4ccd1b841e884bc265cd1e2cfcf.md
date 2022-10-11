# Merge Intervals

[Merge Intervals - LeetCode](https://leetcode.com/problems/merge-intervals/)

## Approach

- Sort the array
- Maintain a start and end variable
    - start = interval[0][0]
    - end = interval[0][1]
- Traverse in the array
    - If the start element of the current interval is less than or equal to end
        - end = Math.max(end,intervals[i][1])
    - else
        - add the current interval to the result array
        - set start as the start of current interval
        - set end as end of current interval
- add the last interval to the result array
- return result array

```java
public int[][] merge(int[][] intervals) {
        List<int[]> res = new ArrayList<int[]>();
        
        if(intervals.length == 0 || intervals[0] == null){
            return res.toArray(new int[0][]);
        }
        
        Arrays.sort(intervals,(a,b) -> a[0] - b[0]);

        int start = intervals[0][0];
        int end = intervals[0][1];
        
        for(int i=0;i<intervals.length;i++){
            if(intervals[i][0] <= end){
                end = Math.max(end,intervals[i][1]);
            }
            else{
                res.add(new int[]{start,end});
                start = intervals[i][0];
                end = intervals[i][1];
            }
        }
        res.add(new int[]{start,end});
        return res.toArray(new int[0][]);
    }
```