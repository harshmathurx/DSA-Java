# Matrix Median (1)

[Code Studio](https://www.codingninjas.com/codestudio/problems/873378?topList=striver-sde-sheet-problems&utm_source=striver&utm_medium=website)

### Problem

Find the median out of all the elements in the 2D Matrix 

We are given a matrix that has sorted rows

**IMP: Only the rows are sorted, not the columns** 

### Naive Approach

- Iterate over every element in the array
- Add the elements to an ArrayList
- Sort the ArrayList
- Find the middle index and return the element at that index

### Optimized Approach

We use Binary Search to optimize the solution 

Why? Because binary search can be applied to any search space from that is monotonic in nature 

We just need to find the range 

Range - 1 to $10^9$