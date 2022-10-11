# Linked List Implementation

### NODE - The most important thing in the linked list

![Untitled](Linked%20List%20Implementation%20d584f72ecfc24f7f885dbe5b51271a0d/Untitled.png)

A singly linked list has only 1 pointer (next) and a value 

A doubly linked list has 2 pointers (previous and next) and a value

```java
public class Node{
	private int val;
	private Node next;

	//Constructors 
	public Node(int val){
		this.val = val;
	}
	
	public Node(int val, Node next){
		this.val = val;
		this.next = next;
	}
}
```

## NOW, The Linked List Class

![Untitled](Linked%20List%20Implementation%20d584f72ecfc24f7f885dbe5b51271a0d/Untitled%201.png)

A linked list has 3 main elements 

1. Head
2. Tail
3. Size

```java
 public class LL{
		private int size;
		private Node head;
		private Node tail;

		//Constructors
		public LL() {
        this.size = 0;
    }	
}
```

## Operations on the Linked List

1. Insertion 
    1. At the start of the LL
    2. At the back of the LL
    3. At a specified index
2. Displaying the linked list 
3. Deletion 

### Methods

- Insertion at the start of LL
    
    To insert the first item of the LL or to insert an item at the 0th index 
    
    **Steps to do that** 
    
    - Create a new node with the value of the element
        - Now we have a node that looks like this
        - Value = 14
        - Next = null
        - The Head of the linked list is not pointing to the new node
    - So we first set the next element
        - node.next = head
            - Now the Linked list looks like
            - node.next = 3
            - head = 3
    - We update the head to point to the new element
        - head = node
    
    ### If the Linked List has a tail
    
    If this is the very first item 
    
    Before insertion
    
    head = null
    
    tail = null
    
    After Insertion
    
    head = node
    
    tail = node
    
    ### IMPORTANT: At the end of insertion, increase the size of the Linked List
    
    ```java
    public void insertFirst(int val){
            Node node = new Node(val);
            node.next = head;
            head = node
            if(tail == null){
                tail = head;
            }
            size += 1;
        }
    ```
    
- Display
    
    We iterate from the first element until we reach null
    
    Steps: 
    
    - Create a temp variable
        - temp = head
    - Iterate until temp = null
        - Print the element at each iteration
        
        ```java
        public void display(){
                Node temp = head;
                while(temp != null) {
                    System.out.print(temp.val + " -> ");
                    temp = temp.next;
                }
                System.out.print("End");
            }
        ```
        
        ## Example
        
        ```java
        public static void main(String[] args) {
        	    LL ll = new LL();
        	    ll.insertFirst(11);
        	    ll.insertFirst(12);
        	    ll.insertFirst(23);
        	    ll.display();
            }
        ```
        
        ![Untitled](Linked%20List%20Implementation%20d584f72ecfc24f7f885dbe5b51271a0d/Untitled%202.png)
        
- Insertion at the last position
    
    When you have the tail 
    
    - If tail is null
        - use the insert first method
    - create a new node
    - the node at which the tail is pointing is the last node
    - So set tail.next = node
    - set tail as the new node added
    
    ```java
    public void insertLast(int val){
            if(tail == null) {
                insertFirst(val);
                return;
            }
            Node node = new Node(val);
            tail.next = node;
            tail = node;
            size++;
        }
    ```
    
    If you don’t have the tail pointer
    
    - Traverse until the last node
        - where [node.next](http://node.next) == null
    - create a node
    - [node.next](http://node.next) = new node
    
- Insertion at a given index
    
    If the index is 0
    
    - use the insert at first method
    
    If the index is the last one 
    
    - Use the insert at last method
    
    - Iterate until the desired index - 1
    - Create a new Node and set the next pointer to index + 1 node
    - set index - 1’s next to the new node
    - increase the size
    
    ![Untitled](Linked%20List%20Implementation%20d584f72ecfc24f7f885dbe5b51271a0d/Untitled%203.png)
    
    ```java
    public void insert(int val, int index){
            if(index == 0){
                insertFirst(val);
                return;
            }
            if(index == size){
                insertLast(val);
                return;
            }
    
            Node temp = head;
            for(int i=1;i<index;i++){
                temp = temp.next;
            }
    
            Node node = new Node(val,temp.next);
            temp.next = node;
            size++;
        }
    ```
    
- Delete First
    
    
    To delete the first element 
    
    Just move the head pointer to the next node 
    
    **WHY?** Because the when the head moves to the next element. If any insert first operation is performed on the Linked List 
    
    The redundant element would be overridden 
    
    Steps
    
    - Move the head to the next node
        - If in case the next element is null
        - The head would be null (that’s what we want)
    - If the head is equal to null
        - tail should be null as well (because the linked list is empty then)
    - reduce the size
    
    ```java
    public int deleteFirst(){
            int value = head.val;
            head = head.next;
            if(head == null){
                tail = null;
            }
            size--;
            return value;
        }
    ```
    
- Get element
    
    ```java
    public Node get(int index){
            Node node = head;
            for(int i=1;i<index;i++) node = node.next;
            return node;
        }
    ```
    
- Delete Last Item
    
    Steps 
    
    - If the last element is the only element
        - Delete First
    
    Otherwise 
    
    - Reach the second last element
    - point the tail to that element
    - set tail . next = null
    
    ```java
    public int deleteLast(){
            if(size <= 1){
                return deleteFirst();
            }
            Node secondLast = get(size - 2);
            int val = tail.value;
            tail = secondLast;
            tail.next = null;
    				size--;
            return val;
        }
    ```
    
- Delete at index
    
    ```java
    public int deleteLast(){
            if(size <= 1){
                return deleteFirst();
            }
            Node secondLast = get(size - 2);
            int val = tail.val;
            tail = secondLast;
            tail.next = null;
            size--;
            return val;
        }
    ```
    
- Find in linked list (Linear Search)
    
    ```java
    public Node find(int value){
            Node node = head;
            while(node != null){
                if(node.val == value) return node;
                node = node.next;
            }
            return null;
        }
    ```