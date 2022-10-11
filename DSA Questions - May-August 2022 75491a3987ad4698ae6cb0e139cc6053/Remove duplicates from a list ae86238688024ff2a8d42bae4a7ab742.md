# Remove duplicates from a list

[Remove Duplicates from Sorted List - LeetCode](https://leetcode.com/problems/remove-duplicates-from-sorted-list)

![Untitled](Remove%20duplicates%20from%20a%20list%20ae86238688024ff2a8d42bae4a7ab742/Untitled.png)

Steps: 

- Iterate over the linked list
- If you find an element is equal to the next element
- change the next pointer of that element to the next of the next element
    - node . next = node.next.next
- return the head (the most significant node)

NOTE:

check if the head is null

if yes, return the head