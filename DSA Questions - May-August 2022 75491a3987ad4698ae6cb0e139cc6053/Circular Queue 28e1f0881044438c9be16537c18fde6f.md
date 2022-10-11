# Circular Queue

*A Circular Queue is a special version of queue where the last element of the queue is connected to the first element of the queue forming a circle.*

![Untitled](Circular%20Queue%2028e1f0881044438c9be16537c18fde6f/Untitled.png)

In a normal Queue, we can insert elements until queue becomes full. But once queue becomes full, we can not insert the next element even if there is a space in front of queue.

![Untitled](Circular%20Queue%2028e1f0881044438c9be16537c18fde6f/Untitled%201.png)

### To implement a circular queue we need

1. end pointer
2. front pointer
3. size

Initialize all of the above with 0

### Constructors

```java
		public CircularQueue(){
        this.data = new int[DEFAULT_SIZE];
    }

    public CircularQueue(int size){
        this.data = new int[size];
    }
```

### Validators

```java
		public boolean isFull(){
        return size == data.length;
    }

    public boolean isEmpty() {
        return size == 0;
    }
```

Whenever we set the value of front or end 

We set it to `end = end % data.length` **OR `front =** front% data.length` OR `i = i%data.length;`

This way we don’t access an element that is out of bounds

When we add an element at end + 1, to reach the first element we need `end%data.length` to reach the element at index 0 

### Insert function

- If the stack is not full, go on and insert
- insert an element at the end pointer
- increment end by 1
- set `end = end % data.length`
- increase the size
- return true

```java
		public boolean insert(int item){
        if(isFull()){
            return false;
        }

        data[end]= item;
        end++;
        end = end% data.length;
        size++;
        return true;
    }
```

### Remove function

```java
	public int remove() throws Exception{
        if(isEmpty()){
            throw new Exception("Queue is empty");
        }
        int removed = data[front];
        front = front% data.length;
        size--;
        return removed;
    }
```

### Display function

```java
	public void display(){
        if(isEmpty()){
            System.out.println("Queue is empty");
            return;
        }
        int i=0;
        do{
            System.out.print(data[i] + " ");
            i++;
            i = i%data.length;
        } while(i!=end);
        System.out.println("END");
    }
```