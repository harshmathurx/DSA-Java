# Majority Element II

[Majority Element II - LeetCode](https://leetcode.com/problems/majority-element-ii/)

## Brute Force

- For every element
- traverse in the rest of the array
- If the element occurs more than n/3 times
- Add it to the list
- return list

## Better

- Use a hashmap
- Keep a key-value pair for each element
- Increase the count of each element at each occurance
- return the elements which have more than n/3 occurrences

## Optimal

Using Boyer Moore’s voting algorithm

```jsx
public List<Integer> majorityElement(int[] nums) {
        int c1 = 0;
        int c2 = 0;
        int num1 = -1;
        int num2 = -1;
        int n = nums.length;
        for(int num: nums){
            if(num == num1){
                c1++;
            }
            else if(num == num2){
                c2++;
            }
            else if(c1 == 0){
                num1 = num;
                c1 = 1;
            }
            else if(c2 == 0){
                num2 = num;
                c2 = 1;
            }
            else{
                c1--;
                c2--;
            }
        }

        List<Integer> res = new ArrayList<Integer>();
        int count1 = 0;
        int count2 = 0;
        for(int num: nums){
            if(num == num1){
                count1++;
            }
            else if(num == num2){
                count2++;
            }
        }
        if(count1 > n/3){
            res.add(num1);
        }
        if(count2 > n/3){
            res.add(num2);
        }
        return res;
    }
```