# Queue Implementation

The implementation of Queue is very similar to the implementation of 

[Stack Implementation ](Stack%20Implementation%202cdd61b1e56147928207e2523e6c1566.md)

Here, we use 2 things

1. Data array 
2. end pointer (initialize with 0)

### Constructors

```java
		public CQueue(){
        this.data = new int[DEFAULT_SIZE];
    }

    public CQueue(int size){
        this.data = new int[size];
    }
```

### Validation function

Here the only pointer we use to keep a track of elements is the END pointer.

So we check the state of the queue using the END pointer

```java
		public boolean isFull(){
        return end == data.length;
    }

    public boolean isEmpty(){
        return end == -1;
    }
```

### Insert Function

- We check if the stack is full or not, if it is not full
    - We add an element at the end index of the array
    - We increment the end pointer by 1, indicating the end of the array
    - return true

```java
		public boolean insert(int item){
        if(isFull()){
            return false;
        }

        data[end] = item;
        end++;
        return true;
    }
```

### Remove Function

We check if the queue is empty or not 

If it is not empty 

We store the first element to be removed in a variable 

Then we loop from index 1 to the end of the queue 

We cope every element at i to the element at i-1

end - - 

return the removed element stored in the array 

```java
	public int remove() throws Exception{
        if(isEmpty()){
            throw new Exception("Queue is empty");
        }
        int removed = data[0];
        for(int i=1;i<end;i++){
            data[i-1] = data[i];
        }
        end--;
        return removed;
    }
```