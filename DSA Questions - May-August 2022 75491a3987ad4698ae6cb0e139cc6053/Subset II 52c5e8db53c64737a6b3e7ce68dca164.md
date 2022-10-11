# Subset II

[Subsets II - LeetCode](https://leetcode.com/problems/subsets-ii/)

## Idea

- Use the principle of inclusion and exclusion
- The only difference here is that we need to skip the duplicate elements

## Approach

- Create a function with parameters
    - List of List of Integers
    - Temporary List of integers
    - input array
    - index
- Sort the input array
- Create a List of List of Integers
- call the recursive function

## Recursive Function

- add a new empty list to the result list
- loop in the input array
- if you find an element i where a[i] == a[i+1]
    - continue
- add a[i] to the temp array
- call the recursive function with index+1

**Backtrack**

- remove the last element of the temp list (the one we just added)

```java
public List<List<Integer>> subsetsWithDup(int[] nums) {
        Arrays.sort(nums);
        List<List<Integer>> res = new ArrayList<>();
        helper(res,new ArrayList<>(),nums,0);
        return res;
    }
    
    public void helper(List<List<Integer>> res, List<Integer> ls, int[] nums, int pos) {
        res.add(new ArrayList<>(ls));
        for(int i=pos;i<nums.length;i++) {
            if(i>pos&&nums[i]==nums[i-1]) continue;
            ls.add(nums[i]);
            helper(res,ls,nums,i+1);     
            ls.remove(ls.size()-1);
        }
    }
```