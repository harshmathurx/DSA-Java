# Reorder a linked list

[Reorder List - LeetCode](https://leetcode.com/problems/reorder-list/)

## Approach

![Untitled](Reorder%20a%20linked%20list%2021f17199a2cb4b0097a4cfb7b292126f/Untitled.png)

Since you can’t access the previous element or iterate backwards

- Find the middle element of the list
- Reverse the list from the middle to the end

Here starts the real solution 

- Place one pointer on the head - head first
- Place another reversed linked list’s head - head second

![Untitled](Reorder%20a%20linked%20list%2021f17199a2cb4b0097a4cfb7b292126f/Untitled%201.png)

Keep iterating from the start of the first list till you reach the middle element 

and follow this

```java
						temp = hf.next;
            hf.next = hs;
            hf = temp;
            
            temp = hs.next;
            hs.next = hf;
            hs = temp;
```

 

```java

public void reorderList(ListNode head) {
        if(head == null || head.next == null){
            return;
        }
        
        ListNode mid = middleNode(head);
        ListNode hf = head;
        ListNode hs = reverseList(mid);
        
        while(hf != null && hs != null){
            ListNode temp = hf.next;
            hf.next = hs;
            hf = temp;
            
            temp = hs.next;
            hs.next = hf;
            hs = temp;
        }
        
        if(hf != null){
            hf.next = null;
        }
    }
```