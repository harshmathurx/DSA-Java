# Reverse a linked list (recursively)

![Untitled](Reverse%20a%20linked%20list%20(recursively)%20d754c1c1120d44d9918fcb70aaaf48ec/Untitled.png)

## Approach

- We keep calling the function recursively until we reach the last node or the tail
- If the node is tail
    - change the tail to head
        - both head and tail are pointing to the same element then
        - return to the previous call
        
        ![Untitled](Reverse%20a%20linked%20list%20(recursively)%20d754c1c1120d44d9918fcb70aaaf48ec/Untitled%201.png)
        
- Now we are at the second last node of the LL
- Set tail .next = node
- then move the tail to the node

![Untitled](Reverse%20a%20linked%20list%20(recursively)%20d754c1c1120d44d9918fcb70aaaf48ec/Untitled%202.png)

- set tail . next to null
- then we return to the previous function call

![Untitled](Reverse%20a%20linked%20list%20(recursively)%20d754c1c1120d44d9918fcb70aaaf48ec/Untitled%203.png)

This happens until we reach our first call and the first element 

which sets the first element to tail and the tail . next to null

```java
public void reverse list(Node node){
        if(node == tail){
            head = tail;
            return;
        }

        reverseList(node.next);

        tail.next = node;
        tail = node;
        tail.next = null;
    }
```