# Count No. of occurrences of an element in an array

### Think long and hard future Harsh

Think about the last and first occurrence of an element in a sorted array

If you have the indexes of last and first occurrence 

We can get the count by last - first + 1

This is because the array is sorted and all the similar elements will be together 

# [0,1,2,3,**4,4,4**,5,6]

```java
		public static void main(String[] args) {
		    int[] nums = {1,2,3,5,6,6,6,7,8,9}; 
		    int res = lastOcc(nums,6) - firstOcc(nums,6) + 1;
	        System.out.println(res);
		}
    
		public static int firstOcc(int[] arr,int target){
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
    
    public static int lastOcc(int[] arr,int target){
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