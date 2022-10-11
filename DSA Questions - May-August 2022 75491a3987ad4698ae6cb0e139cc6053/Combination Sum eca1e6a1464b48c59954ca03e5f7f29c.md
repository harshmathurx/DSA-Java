# Combination Sum

## Idea

- Use inclusion-exclusion

## Approach

- if you reach the end of the array
    - if the target is now 0
        - add the temp list to the result list
    - return
- if the value of the target is less than or equal to the element at the current index
    - add the current element to the temp list
    - call the recursive function with the target at `target - arr[i]`
    - remove the last element of the temp list (the one we just added) // this is to backtrack
- call the recursive function on the next index

```java
public List<List<Integer>> combinationSum(int[] candidates, int target) {
        List<List<Integer>> res = new ArrayList<List<Integer>>();
        sum(res,new ArrayList<Integer>(),0,candidates,target);
        return res;
    }
    
    public void sum(List<List<Integer>> res,List<Integer> temp, int i,int[] arr,int target){
        if(i == arr.length){
            if(target == 0){
                res.add(new ArrayList<Integer>(temp));
            }
            return;
        }
        
        if(arr[i] <= target){
            temp.add(arr[i]);
            sum(res,temp,i,arr,target-arr[i]);
            temp.remove(temp.size()-1);
        }
        sum(res,temp,i+1,arr,target);
    }
```