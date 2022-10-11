# Insertion using Recursion

```java
public void insertRec(int val, int index){
	head = insertRec(val,index,head);
}

public Node insertRec(int val,int index,Node node){
	if(index == 0){
		Node temp = new Node(val,node);
		size++;
		return temp;
	}
	node.next = insertRec(val,index--,node.next);
	return node;
}
```

## The idea

The second method returns the node that we are currently on 

So we start from the head 

we keep moving forward until we reach the node we want to insert at 

When we reach the index where we want to insert 

Create a new node 

increase the size 

NOW 

new node . next = what is in my function call