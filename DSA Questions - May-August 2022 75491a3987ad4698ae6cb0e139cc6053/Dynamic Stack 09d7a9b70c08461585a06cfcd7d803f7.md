# Dynamic Stack

## The dynamic stack will extend the Stack class

Constructors

```java
	protected DynamicStack(){
        super();
    }

    public DynamicStack(int size){
        super(size);
    }
```

### The only function we need to change is the push function, we override the push function from the Stack class

```java
@Override
    public boolean push(int item) {
        if(isFull()){
            int[] temp = new int[data.length*2];
            for(int i=0;i<data.length;i++){
                temp[i] = data[i];
            }

            data = temp;
            super.push(item);
        }
        return super.push(item);
    }
```