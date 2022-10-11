# Majority Elements

[Majority Element - LeetCode](https://leetcode.com/problems/majority-element)

## Brute Force

- For every element of the array
- Traverse in the rest of the array
- Count the number of occurrences
- If the occurrences are more than n/2 times
- return element

## Better

- Use a hash map
- Keep a key value pair
- Travers through the array
- For every element, increase the count by 1
- return the element with count more than n/2

## Optimal Approach

NOTE - USE  MOORE’S VOTING ALGORITHM 

```jsx
public int majorityElement(int[] nums) {
        int count = 0;
        int candidiate = 0;
        for(int num: nums){
            if(count == 0){
                candidiate = num;
            }
            count += num == candidiate ? 1 : -1;
        }
        return candidiate;
    }
```