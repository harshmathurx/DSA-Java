# Search in a sorted 2D Matrix

[Search a 2D Matrix - LeetCode](https://leetcode.com/problems/search-a-2d-matrix)

## Naive Approach

- Traverse in the rows
    - traverse in the column to check every element
    - if found, return true
- After traversal
- If not found, return false

## Better Approach

**IMP - The rows of the matrix are sorted**

- Traverse the rows
- Perform a binary search on the elements of each row

## Even Better Approach

![Untitled](Search%20in%20a%20sorted%202D%20Matrix%2039baaff5b6fc460f9a08a85a758d9df4/Untitled.png)

- Place pointers r and c at the top right corner of the matrix
- Use a tweaked approach of binary search
- If the element is less than the target
    - move to the next row or r++;
- If the element is greater than the target
    - move to the previous col or c - -
- If found, return true
- Else return false

 

```java
public boolean searchMatrix(int[][] matrix, int target) {
        int r = 0;
        int c = matrix[0].length - 1;
        
        while(r >=0 && c>=0 && r<matrix.length){
            if(matrix[r][c] == target){
                return true;
            }
            else if(matrix[r][c] > target){
                c--;
            }
            else if(matrix[r][c] < target){
                r++;
            }
        }
        return false;
    }
```

## Optimal Solution

- Use binary search on the matrix

[https://youtu.be/ZYpYur0znng?t=424](https://youtu.be/ZYpYur0znng?t=424)

```java
public boolean searchMatrix(int[][] matrix, int target) {
        int n = matrix.length;
        int m = matrix[0].length;
        
        int low = 0;
        int high = (n*m) - 1;
        
        while(low<=high){
            int mid = low + (high-low)/2;
            
            if(matrix[mid/m][mid%m] == target){
                return true;
            }
            else if(matrix[mid/m][mid%m] > target){
                high = mid - 1;
            }
            else{
                low = mid + 1;
            }
        }
        return false;
    }
```