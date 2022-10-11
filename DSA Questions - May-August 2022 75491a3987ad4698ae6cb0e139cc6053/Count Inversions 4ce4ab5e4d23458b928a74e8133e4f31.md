# Count Inversions

[Count Inversions in an array | Set 1 (Using Merge Sort) - GeeksforGeeks](https://www.geeksforgeeks.org/counting-inversions/)

# Brute Force Approach

- Traverse in the array
    - For each element i, traverse from i to the end of the array
        - if a[i] > a[j] and i<j
        - increase the count of inversions
- return the count

# Merge Sort Technique