# Reverse K group elements

[Reverse Nodes in k-Group - LeetCode](https://leetcode.com/problems/reverse-nodes-in-k-group)

## Approach

- We find the count, i.e. the number of times we need to reverse the elements of a group.
    - count = length of list / k
- We start from head and start reversing elements in a part of a list
- we do this count no. of times

```java
public ListNode reverseKGroup(ListNode head, int k) {
        if (k <= 1 || head == null) {
            return head;
        }

        ListNode current = head;
        ListNode prev = null;

				int length = getLength(head);
				int count = length / k;
		        while (count > 0) {
		            ListNode last = prev;
		            ListNode newEnd = current;
		
		            ListNode next = current.next;
		            for (int i = 0; current != null && i < k; i++) {
		                current.next = prev;
		                prev = current;
		                current = next;
		                if (next != null) {
		                    next = next.next;
		                }
		            }
		
		            if (last != null) {
		                last.next = prev;
		            } else {
		                head = prev;
		            }
		
		            newEnd.next = current;
		
		            prev = newEnd;
								count--;
		        }
		     return head;
    }
    
    public int getLength(ListNode head) {
				ListNode node = head;
				int length = 0;
				while (node != null) {
					length++;
					node = node.next;
				}
				return length;
		}
```