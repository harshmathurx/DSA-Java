# Binary Search on a Reverse Array (Descending)

[https://www.youtube.com/watch?v=YbkELwnGRdo&list=PL_z_8CaSLPWeYfhtuKHj-9MpYb6XQJ_f2&index=3](https://www.youtube.com/watch?v=YbkELwnGRdo&list=PL_z_8CaSLPWeYfhtuKHj-9MpYb6XQJ_f2&index=3)

![Untitled](Binary%20Search%20on%20a%20Reverse%20Array%20(Descending)%2027559bf2c517451bab6e31918b97cb55/Untitled.png)

This method will work the same as a normal binary search

The only difference is in the condition for setting new low and high values 

**Normal Binary Search** 

```java
if(x < arr[mid]){
	end = mid - 1;
}
else{
	start = mid + 1;
}
```

**Reverse Binary Search**

Now because the answer may lie in the left side or the right side of the array 

We set the bounds accordingly 

```java
if(x < arr[mid]){
	start = mid + 1;
}
else{
	end = mid - 1;
}
```