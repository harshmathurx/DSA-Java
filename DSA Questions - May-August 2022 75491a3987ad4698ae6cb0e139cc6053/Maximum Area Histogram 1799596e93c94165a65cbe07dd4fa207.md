# Maximum Area Histogram

![Untitled](Maximum%20Area%20Histogram%201799596e93c94165a65cbe07dd4fa207/Untitled.png)

[Area of largest rectangle in Histogram - Arrays - Tutorial](https://takeuforward.org/data-structure/area-of-largest-rectangle-in-histogram/)

[https://www.youtube.com/watch?v=J2X70jj_I1o&list=PL_z_8CaSLPWdeOezg68SKkeLN4-T_jNHd&index=7](https://www.youtube.com/watch?v=J2X70jj_I1o&list=PL_z_8CaSLPWdeOezg68SKkeLN4-T_jNHd&index=7)

## Approach

- Find the nearest smaller element to the left - store it in the left array
- Find the nearest smaller element to the right - store it in the right array
- Find the maximum area possible

Here, we are not storing the smallest element in the stack
We are storing the index of the smallest element in the stack 

We compare the value of the element with the index at the top of the stack when we are popping it 

```java
int maxA = 0;
for (int i = 0; i < n; i++) {
		maxA = Math.max(maxA, heights[i] * (rightSmall[i] - leftSmall[i] + 1));
}
```

## For Nearest Smaller Element to Left

If the stack is empty we push 0 into the stack

```java
		for (int i = 0; i < n; i++) {
            while (!st.isEmpty() && heights[st.peek()] >= heights[i]) {
                st.pop();
            }

            if (st.isEmpty()) leftSmall[i] = 0;
            else leftSmall[i] = st.peek() + 1;
            st.push(i);
		 }
```

## For Nearest Smaller Element to Right

If the stack is empty, we push n - 1 into the stack

```java
for (int i = n - 1; i >= 0; i--) {
            while (!st.isEmpty() && heights[st.peek()] >= heights[i]) {
                st.pop();
            }

            if (st.isEmpty()) rightSmall[i] = n - 1;
            else rightSmall[i] = st.peek() - 1;

            st.push(i);
  }
```