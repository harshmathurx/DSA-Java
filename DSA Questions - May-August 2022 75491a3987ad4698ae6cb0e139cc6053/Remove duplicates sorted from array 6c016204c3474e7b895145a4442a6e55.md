# Remove duplicates sorted from array

[Remove Duplicates from Sorted Array - LeetCode](https://leetcode.com/problems/remove-duplicates-from-sorted-array)

## Approach

- Place 2 pointers i and j at 0 and 1 index respectively
- Loop through the array
    - if element at i is not equal to element at j
        - move the i pointer ahead
        - replace the element at i with element at j
    - Else
        - do nothing
        - just keep iterating to find an element not equal to i
- return i+1;
- we return i+1 because at the end of the iteration, i would be at the end of the non duplicate subarray

```java
public int removeDuplicates(int[] nums) {
        if(nums.length == 0) return 0;
        
        int i=0;
        
        for(int j=1;j<nums.length;j++){
            if(nums[j] != nums[i]){
                i++;
                nums[i] = nums[j];
            }
        }
        
        return i+1;
    }
```