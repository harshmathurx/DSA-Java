# Number of times a sorted array is rotated

[Find Minimum in Rotated Sorted Array - LeetCode](https://leetcode.com/problems/find-minimum-in-rotated-sorted-array/)

### Key

- To find the number of times a sorted array is rotated
- Find the min element of the array
- No. of times an array is rotated = index of the min element

![Untitled](Number%20of%20times%20a%20sorted%20array%20is%20rotated%20f07046f5c3d140ad905995afafbe6d9e/Untitled.png)

### The approach is to keep trimming down the search space till you have only 1 element left

When the loop terminates, we will only have 1 element left 

when low = high

**The only difference in this binary search is the conditions** 

**We check which part to eliminate based on the element at the end of the array** 

### When the end element is greater than the mid element

- You need to check in the right array
- The pivot lies in the right part

# [5,6,1,2,3,4]

```java
if(arr[end] > arr[mid]){
	end = mid;
}
```

### When the end element is less than the

- The pivot lies in the left part of the array
- Search in the left array

# [5,6,1]

```java
if(arr[end] < arr[mid]){
	start = mid + 1;
}
```

# **PLEASE PERFORM A DRY RUN**

## Entire code

```java
public int noOfRotations(int[] arr) {
        int start = 0;
        int end = arr.length-1;
        while(start < end){
            int mid = start + (end - start)/2;
            
            if(arr[end] > arr[mid]){
                end = mid;
            }
            else if(arr[end] < arr[mid]){
                start = mid + 1;
            }
        }
        return start;
    }
```