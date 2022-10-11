# Length of a linked List cycle

### Approach

- Use the fast and slow pointer approach to confirm if there is a cycle
- when the fast and slow pointer reach the same node
- Iterate again but only using small pointer
    - count the number of elements
    - until it reaches the fast pointer again
    - return the count

 

```java
public static int lengthOfCycle(Node head){
        Node fast = head;
        Node slow = head;
        while(fast != null && fast.next != null){
            fast = fast.next.next;
            slow = slow.next;
            if(fast == slow){
                int len = 0;
                do{
                    slow = slow.next;
                    len++;
                } while(slow != fast);
                return len;
            }
        }
        return 0;
    }
```

[Linked List Cycle II](Length%20of%20a%20linked%20List%20cycle%20d201154d1a4545bb9f2ceca6a2a9ce79/Linked%20List%20Cycle%20II%2053096961b0674fadb1cb4d5e6c4684a7.md)