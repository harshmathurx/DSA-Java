# Next Permutation

[Next Permutation - LeetCode](https://leetcode.com/problems/next-permutation)

### Approach

- Traverse from the back
- Find the an element i where A[i] < A[i+1]
- Again traverse from the back and find an j element where
- A[j] > A[j+1]
- Swap the elements i and j
- Reverse the elements from i to the last element

### Code

```java
public void nextPermutation(int[] nums) {
        if(nums == null || nums.length == 0){
            return;
        }
        
        int i=nums.length - 2;
        while(nums[i]>nums[i+1] && i>0) i--;
        int j = nums.length - 1;
        while(nums[i]<nums[j]) j--;
        swap(nums,i,j);
        reverse(nums,i,nums.length-1);
    }
    
    public void swap(int nums[], int a, int b){
        int temp = nums[a];
        nums[a] = nums[b];
        nums[b] = temp;
    }
    
    public void reverse(int A[], int i,int j){
        while(i<=j){
            swap(A,i,j);
            i++;
            j--;
        }
    }
```