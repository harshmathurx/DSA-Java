# Add two numbers

[Add Two Numbers - LeetCode](https://leetcode.com/problems/add-two-numbers)

## The idea

We have 2 reversed lists 

We need to convert them into integers and add them 

But what if we add them as they are 

like we used to in middle school 

![Untitled](Add%20two%20numbers%20b0aaf08445de4887ba2585d867f3afd2/Untitled.png)

## Approach

- Check if any of the lists is empty
- If not, start from a new node (dummy)
- Keep a carry variable
- now traverse through the list
    - add node1 and node2 and the carry (initially the carry is 0)
    - divide the carry by 10
    - move to the next node
    - next = sum % 10
    - the carry will be handled in the next iteration

```java
public ListNode addTwoNumbers(ListNode l1, ListNode l2) {
        ListNode dummyHead = new ListNode(0);
        ListNode curr = dummyHead;
        int carry = 0;
        while (l1 != null || l2 != null || carry != 0) {
            int x = (l1 != null) ? l1.val : 0;
            int y = (l2 != null) ? l2.val : 0;
            int sum = carry + x + y;
            carry = sum / 10;
            curr.next = new ListNode(sum % 10);
            curr = curr.next;
            if (l1 != null)
                l1 = l1.next;
            if (l2 != null)
                l2 = l2.next;
        }
        return dummyHead.next;
```