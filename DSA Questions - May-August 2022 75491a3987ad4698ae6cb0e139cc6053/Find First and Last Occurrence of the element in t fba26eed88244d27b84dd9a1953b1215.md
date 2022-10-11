# Find First and Last Occurrence of the element in the array

[Find First and Last Position of Element in Sorted Array - LeetCode](https://leetcode.com/problems/find-first-and-last-position-of-element-in-sorted-array)

## Approach

First Occurrence 

- Find the element using binary search
- When you find the element at the mid index
- Trim the search space to the left array. Why?
- because we need the first occurrence and that lies in the left occurrence

Last Occurrence

- Perform the same steps as the first occurrence
- The only change is that you need to trim the search space to the right array

```java
	public int[] searchRange(int[] nums, int target) {
        int first = firstOcc(nums,target);
        int last = lastOcc(nums,target);
        
        return new int[] {first,last};
    }
    
    public int firstOcc(int[] arr,int target){
        int start = 0;
        int res = -1;
        int end = arr.length - 1;
        int mid = 0;
        while(start<=end){
            mid = start + (end-start)/2;
            if(arr[mid] == target){
                res = mid;
                end = mid -1;
            }
            else if(target < arr[mid]) end = mid - 1;
            else start = mid + 1;
        }
        return res;
    }
    
    public int lastOcc(int[] arr,int target){
        int start = 0;
        int end = arr.length - 1;
        int res = -1;
        int mid = 0;
        while(start<=end){
            mid = start + (end-start)/2;
            if(arr[mid] == target){
                res = mid;
                start = mid + 1;
            }
            else if(target < arr[mid]) end = mid - 1;
            else start = mid + 1;
        }
        return res;
    }
```