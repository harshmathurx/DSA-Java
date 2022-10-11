# Order Agnostic Binary Search

```java
public int search(int[] nums, int target) {
        int start=0;
        int end=nums.length-1;
        boolean isasc=nums[start]<nums[end];
        while(start<=end){
            int mid=start+(end-start)/2;
            if(nums[mid]==target){
                return mid;
            }
            if(isasc){
                if(target<nums[mid]){
                    end=mid-1;
                }
                else if(target>nums[mid]){
                    start=mid+1;
                }
            }
            else
                if(target<nums[mid]){
                    end=mid-1;
                }
                else if(target>nums[mid]){
                    start=mid+1;
                }
        }
        return -1;
    }
```