# Stack Implementation

![Untitled](Stack%20Implementation%202cdd61b1e56147928207e2523e6c1566/Untitled.png)

The stack has 3 primary functions 

1. Push 
2. Pop 
3. Peek

### Stacks work on the principle of LIFO - Last in first out

### To implement a stack class

We need

- An array of data, int[] data
- A pointer to keep a track of the latest element

### Constructors

```java
	public Stamk(int size){
        this.data = new int[size];
    }

    public Stamk(){
        this(DEFAULT_SIZE);
    }
```

### Function to maintain rigidity

```java
	public boolean isFull(){
        return ptr == data.length;
    }

    public boolean isEmpty(){
        return ptr == -1;
    }
```

### Push Function

```java
	public boolean push(int item){
        if(isFull()){
            new StamkException("Stack is full");
        }
        ptr++;
        data[ptr] = item;
        return true;
    }
```

### Pop Function

```java
	public int pop() throws Exception {
        if(isEmpty()){
            throw new StamkException("Cannot pop from empty stack");
        }

        int removed = data[ptr];
        ptr--;
        return removed;
    }
```

### Peek Function

```java
		public int peek() throws Exception {
        if (isEmpty()) {
            throw new StamkException("Cannot peek from empty stack");
        }

        return data[ptr];
    }
```