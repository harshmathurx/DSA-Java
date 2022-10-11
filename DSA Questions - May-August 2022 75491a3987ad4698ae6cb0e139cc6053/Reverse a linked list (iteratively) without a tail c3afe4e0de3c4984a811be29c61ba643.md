# Reverse a linked list (iteratively) without a tail pointer

[Reverse Linked List - LeetCode](https://leetcode.com/problems/reverse-linked-list/)

## Approach

- Use 3 pointers
    - previous
    - present
    - next
- Iterate from head to the last element
- Set the present as the previous
- Set present as next
- Set next as next to next

```java
public ListNode reverseList(ListNode head) {
        if(head == null){
            return head; 
        }
        ListNode prev = null;
        ListNode pres = head;
        ListNode next = pres.next;
        // prev.next = pres;
        
        while(pres != null){
            pres.next = prev;
            prev = pres;
            pres = next;
            if(next != null){
                next = next.next;                
            }
        }
        head = prev;
        return head;
    }
```