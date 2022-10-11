# The intersection of linked list

[Intersection of Two Linked Lists - LeetCode](https://leetcode.com/problems/intersection-of-two-linked-lists)

[https://youtu.be/u4FWXfgS8jw?t=736](https://youtu.be/u4FWXfgS8jw?t=736)

```java
	public ListNode getIntersectionNode(ListNode headA, ListNode headB) {
        ListNode d1 = headA;
        ListNode d2 = headB;
        
        while(d1 != d2){
            d1 = (d1 == null) ? headB : d1.next;
            d2 = (d2 == null) ? headA : d2.next;
        }
        
        return d1;
    }
```