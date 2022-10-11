# Find the duplicate element

[Find the Duplicate Number - LeetCode](https://leetcode.com/problems/find-the-duplicate-number/solution/)

### Approach

### Code

```java
public int findDuplicate(int[] nums) {
        int[] temp = new int[nums.length];
        Arrays.fill(temp,0);
        for(int i=0;i<nums.length;i++){
            if(temp[nums[i]] == 0){
                temp[nums[i]] = 1;
            }
            else{
                return nums[i];
            }
        }
        return -1;
    }
```