# Find an element in a sorted rotated array

[Search in Rotated Sorted Array - LeetCode](https://leetcode.com/problems/search-in-rotated-sorted-array/)

![Untitled](Find%20an%20element%20in%20a%20sorted%20rotated%20array%20d087a3df910144199f566fce91e18ac4/Untitled.png)

Case 1

if nums[mid] == target

return mid

Case 2

- when the middle element is greater than or equal to start
- you are in the left part of the array
    
    if start ≤ target and target < middle element
    
    search in the left array 
    
    end = mid - 1
    
    else
    
    search in the right array
    
    start = mid + 1
    
     
    

Case 3

- when the start element is greater than the mid element
- this means you are in the right part
    
    if end ≥ target and target > mid
    
    start = mid + 1
    
    else
    
    end = mid - 1 
    

Case 4

if not found 

return -1

```java
public int search(int[] nums, int target) {
        int start =0; 
        int end = nums.length -1;
        
        while(start <= end){
            int mid = start + (end - start)/2; 
            
            if(nums[mid] == target ){
                return mid;
            }
            
            //left half is sorted
            if( nums[start] <= nums[mid]){
                
                //element lies in the left
                if(nums[start] <= target && target < nums[mid]){
                    end = mid-1;
                }
                
                //element lies in the right
                else{
                start = mid +1;
                }
            }
            
            //left half is not sorted
            else{
                
                //element lies in the right
                if(nums[end] >= target && target > nums[mid]){
                    start= mid+1;
                }
                
                //element lies in the left
                else{
                    end = mid-1;
                }
            }
        }
        return -1;
    }
```