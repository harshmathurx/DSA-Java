# Middle of a linked list

[Middle of the Linked List - LeetCode](https://leetcode.com/problems/middle-of-the-linked-list/)

## Approach

- Use the fast and slow pointer
- Move the fast pointer twice faster than the slow pointer
- Do a complete traversal using the fast pointer
- When the fast reaches the end of the linked list, the slow pointer would be at the middle
- return slow

```java
public ListNode middleNode(ListNode head) {
        ListNode fast = head;
        ListNode slow = head;
        
        while(fast != null && fast.next != null){
            fast = fast.next.next;
            slow = slow.next;
        }
        return slow;
    }
```