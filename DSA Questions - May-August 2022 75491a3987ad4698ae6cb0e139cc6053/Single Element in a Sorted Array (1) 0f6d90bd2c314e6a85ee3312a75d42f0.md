# Single Element in a Sorted Array (1)

[Single Element in a Sorted Array - LeetCode](https://leetcode.com/problems/single-element-in-a-sorted-array)

[https://www.youtube.com/watch?v=PzszoiY5XMQ&list=PLgUwDviBIf0p4ozDR_kJJkONnb1wdx2Ma&index=64](https://www.youtube.com/watch?v=PzszoiY5XMQ&list=PLgUwDviBIf0p4ozDR_kJJkONnb1wdx2Ma&index=64)

## Watch the video, it is a hard problem

```java
public int singleNonDuplicate(int[] nums) {
        int low = 0;
        int high = nums.length - 2;
        
        while (low <= high) {
            int mid = (low + high) / 2;
	     
            if (mid % 2 == 0) {
                // Checking whether we are in right half
                if (nums[mid] != nums[mid + 1]) 
                    
                    //Shrinking the right half
                    high = mid - 1; 
                else
                    // Shrinking the left half
                    low = mid + 1; 
            } else {
                // Checking whether we are in right half
                if (nums[mid] == nums[mid + 1])
                    //Shrinking the right half
                    high = mid - 1; 
                else
                    // Shrinking the left half
                    low = mid + 1; 
            }
        }
        return nums[low];
    }
```