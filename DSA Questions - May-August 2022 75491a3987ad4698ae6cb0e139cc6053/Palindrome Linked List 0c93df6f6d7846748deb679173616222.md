# Palindrome Linked List

Asked in - Microsoft, Amazon, LinkedIn, Google, Apple 

## Appraoch

- find the middle element of the list
- reverse the linked list from the middle to the end
- compare every element

![Untitled](Palindrome%20Linked%20List%200c93df6f6d7846748deb679173616222/Untitled.png)

```java
public boolean isPalindrome(ListNode head) {
        ListNode mid = middleNode(head);
        ListNode secondHead = reverseList(mid);
        ListNode reverseHead = secondHead;
            
        while(secondHead != null && head.next != null){
            if(head.val !=  secondHead.val){
                return false;
            }
            head = head.next;
            secondHead = secondHead.next;
        }
        return true;
    }
    
    public ListNode middleNode(ListNode head) {
        ListNode fast = head;
        ListNode slow = head;
        
        while(fast != null && fast.next != null){
            fast = fast.next.next;
            slow = slow.next;
        }
        return slow;
    }
    
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