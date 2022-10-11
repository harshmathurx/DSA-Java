# Remove Kth Node from the back

[Remove Nth Node From End of List - LeetCode](https://leetcode.com/problems/remove-nth-node-from-end-of-list/)

## Approach

- get the length of the list
- if n is equal to the length of the list
    - return the head’s next element
    - because we anyway need to remove the first element
- reach the element which we have to remove: length - n - 1
- just set the next element of that node to the next of the next node

```java
public ListNode removeNthFromEnd(ListNode head, int n) {
        ListNode temp = head;
        int counter = 1; //get length
        while (temp.next != null) {
            temp = temp.next;
            counter++;
        }

        if (counter == n) {
            return head.next;
        }

        temp = head;
        for (int i = 0; i < counter - n - 1; i++) {
            temp = temp.next;
        }
        temp.next = temp.next.next;
        return head;
    }
}
```