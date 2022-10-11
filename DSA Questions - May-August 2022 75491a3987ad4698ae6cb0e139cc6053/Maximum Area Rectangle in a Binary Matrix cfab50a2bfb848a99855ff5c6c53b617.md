# Maximum Area Rectangle in a Binary Matrix

[Maximal Rectangle - LeetCode](https://leetcode.com/problems/maximal-rectangle/)

[https://www.youtube.com/watch?v=St0Jf_VmG_g&list=PL_z_8CaSLPWdeOezg68SKkeLN4-T_jNHd&index=8](https://www.youtube.com/watch?v=St0Jf_VmG_g&list=PL_z_8CaSLPWdeOezg68SKkeLN4-T_jNHd&index=8)

![Untitled](Maximum%20Area%20Rectangle%20in%20a%20Binary%20Matrix%20cfab50a2bfb848a99855ff5c6c53b617/Untitled.png)

## Approach

- Watch the video regardless
- We use the function, max area of the histogram on all the 1D arrays in the matrix
- We pass the function an array with all the values of previous arrays added to it
- We return the maximum area out of all the matrices

## Idea

- First, calculate the max area of the histogram for the very first array in the matrix
- Then loop from index 1 to index n - 1
    - Add all the elements of the ith matrix in the array that we created
    - reset the array
        - If the element is 0, change the element of the array to 0
        - otherwise, add it (it is 1)
    - Calculate the max area of the histogram
- return maxArea

## Code

```java
		public int maximalRectangle(char[][] matrix) {
        if(matrix == null || matrix.length == 0 || matrix[0].length == 0) return 0;

        int[] arr = new int[matrix[0].length];
        
        for(int i = 0; i < matrix[0].length; i ++){
            if(matrix[0][i] == '1') arr[i] = 1;
        }
        
        int maxArea = MAH(arr);
        
        for(int i = 1; i < matrix.length; i ++){
            resetHeight(matrix, arr, i);
            maxArea = Math.max(result, MAH(arr));
        }

        return maxArea;
    }
```

Reset Heights function 

```java
		private void resetHeight(char[][] matrix, int[] height, int row){
        for(int i = 0; i < matrix[0].length; i ++){
            if(matrix[row][i] == '1') height[i] += 1;
            else height[i] = 0;
        }
    }
```

[Maximum Area Histogram](Maximum%20Area%20Histogram%201799596e93c94165a65cbe07dd4fa207.md)

```java
public int MAH(int[] heights) {
        int n = heights.length;
        int maxArea = 0;
        int[] left = new int[n];
        int[] right = new int[n];
        Stack<Integer> st = new Stack<Integer>();
        
        //nearest smaller element to left
        for(int i=0;i<n;i++){
            while(!st.isEmpty() && heights[st.peek()] >= heights[i]){
                st.pop();
            }
            if(st.isEmpty()){
                left[i] = 0;
            }
            else{
                left[i] = st.peek() + 1;
            }
            st.push(i);
        }
        
        while(!st.isEmpty()){
            st.pop();
        }
        
        //nearest smaller element to right
        for(int i=n-1;i>=0;i--){
            while(!st.isEmpty() && heights[st.peek()] >= heights[i]){
                st.pop();
            }
            if(st.isEmpty()){
                right[i] = n-1;
            }
            else{
                right[i] = st.peek() - 1;
            }
            st.push(i);
        }
        
        for(int i=0;i<n;i++){
            maxArea = Math.max(maxArea,heights[i] * (right[i]-left[i]+1));
        }
        return maxArea;
    }
}
```