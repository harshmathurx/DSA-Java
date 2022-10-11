# Doubly Linked List

It is exactly like a singly Linked list 

The only difference that stays is in the Node class 

We have an extra pointer called previous 

![Untitled](Doubly%20Linked%20List%201c02d000a2da44dda5f137574a2a0295/Untitled.png)

The previous of head points null and the next of of tail points to null  

```java
public class Node{
	private Node next;
	private Node prev;
	int val;
}
```

## The Doubly Linked List Class

```java
package com.harsh;

public class DLL {

    private Node head;
    private int size;

    public void DLL(){
        this.size = 0;
    }
    public void insertFirst(int val){
        Node node = new Node(val);
        node.next = head;
        node.prev = null;
        if(head != null){
            head.prev = node;
        }
        head = node;
    }

    public void displayRev(){
        Node temp = head;
        while(temp.next != null){
            temp = temp.next;
        }
        while(temp != null){
            System.out.print(temp.val + " -> ");
            temp = temp.prev;
        }
        System.out.print("END");
    }

    public void insertAfter(int after,int val){
        Node p = find(after);
        if(p == null){
            System.out.println("Give node does not exist");
            return;
        }
        Node node = new Node(val);
        p.next = node;
        node.prev = p;
        node.next = null;
        if(node.next == null){
            node.next.prev = node;
        }
    }

    public Node find(int val){
        Node node = head;
        while(node != null){
            if(node.val == val){
                return node;
            }
            node = node.next;
        }
        return null;
    }

    public void display(){
        Node temp = head;
        while(temp != null){
            System.out.print(temp.val + " -> ");
            temp = temp.next;
        }
        System.out.print("END");
    }

    public void insertLast(int val){
        Node node = new Node(val);
        if(head == null){
            head = node;
            head.next = null;
            head.prev = null;
            return;
        }

        Node temp = head;
        while(temp.next != null){
            temp = temp.next;
        }
        node.prev = temp;
        temp.next = node;
        node.next = null;
    }

    private class Node{
        int val;
        Node next;
        Node prev;

        public Node(int val){
            this.val = val;
        }

        public Node(int val, Node next) {
            this.val = val;
            this.next = next;
        }
    }
}
```