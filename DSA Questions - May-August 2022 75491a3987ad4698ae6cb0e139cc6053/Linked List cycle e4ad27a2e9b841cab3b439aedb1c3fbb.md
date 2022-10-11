# Linked List cycle

[Linked List Cycle - LeetCode](https://leetcode.com/problems/linked-list-cycle/)

## Use the fast and slow pointer approach

- Keep 2 pointers at the head - fast and slow
- in every iteration, make the slow pointer move 1 element and make the fast pointer move 2 elements
- If at any point the fast pointer and the slow pointer are at the same element again, there is a cycle
- loop until the fast pointer reaches null or the next element of the fast pointer is null

  

```java
public boolean isCyclePresent(Node head){
        Node fast = head;
        Node slow = head;
        while(fast != null && fast.next != null){
            fast = fast.next.next;
            slow = slow.next;
            if(fast == slow){
                return true;
            }
        }
        return false;
    }
```