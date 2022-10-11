# Dutch National Flag

To sort an array with 3 numbers 

We use an infinite swapping loop until the array is sorted 

[Sort an array of 0s, 1s and 2s - GeeksforGeeks](https://www.geeksforgeeks.org/sort-an-array-of-0s-1s-and-2s/)

## Approach

- 3 Pointers - low, mid, high
- place low and mid at 0
- place high at the end of the array
- while (mid ≤ high)
    - if the element at mid = 0
        - swap low and mid
        - mid++
        - low++
    - if the element at mid = 1
        - mid++
    - if the element at mid = 2
        - swap mid and high
        - high ++