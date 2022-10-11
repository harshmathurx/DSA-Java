# Rotate a linked list

[Rotate List - LeetCode](https://leetcode.com/problems/rotate-list/submissions/)

## Approach

Make the linked list a circular linked list and break the link in between 

- Find the length of the list
- find the number of rotations you need to perform
- find the number of elements you need to skip
- Set next of the last node to head

```java
public ListNode rotateRight(ListNode head, int k) {
        if(k<=0 || head == null || head.next == null) return head;
        
        ListNode last = head;
        int length = 1;
        while(last.next != null){
            last = last.next;
            length++;
        }
        
        last.next = head;
        
        int rotations = k % length;
        int skip = length - rotations;
        
        ListNode newLast = head;
        for(int i=0;i<skip - 1;i++){
            newLast = newLast.next;
        }
        
        head = newLast.next;
        newLast.next = null;
        
        return head;
    } 
```