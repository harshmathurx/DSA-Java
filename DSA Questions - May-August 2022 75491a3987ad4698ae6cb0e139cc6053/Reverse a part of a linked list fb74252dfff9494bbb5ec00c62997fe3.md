# Reverse a part of a linked list

[Reverse Linked List II - LeetCode](https://leetcode.com/problems/reverse-linked-list-ii/)

## What we need

- The element previous to the start of the list
- The pointer L (the new end of the LL)

![Untitled](Reverse%20a%20part%20of%20a%20linked%20list%20fb74252dfff9494bbb5ec00c62997fe3/Untitled.png)

```jsx
public ListNode reverseBetween(ListNode head, int left, int right) {
        if(left == right){
            return head;
        }
        
        ListNode curr = head;
        ListNode prev = null;
        for(int i=0;curr != null && i<left-1;i++){
            prev = curr;
            curr = curr.next;
        }
        
        ListNode last = prev;
        ListNode newEnd = curr;
        
        ListNode next = curr.next;
        for(int i=0;curr != null && i<right - left + 1;i++){
            curr.next = prev;
            prev = curr;
            curr = next;
            if(next != null){
                next = next.next;
            }
        }
        
        if(last != null){
            last.next = prev;
        }
        else{
            head = prev;
        }
        newEnd.next = curr;
        return head;
    }
```