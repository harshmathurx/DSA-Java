# Delete a given node in O(1) time

[Delete Node in a Linked List - LeetCode](https://leetcode.com/problems/delete-node-in-a-linked-list/)

![Untitled](Delete%20a%20given%20node%20in%20O(1)%20time%207bb9b384ec15419eb13c0cc03d8ea427/Untitled.png)

## Approach

This is probably the best leetcode problem I’ve come across 

- Do not delete the node
- Copy the value of the next node to the current node
- point the next of the node to the next of the next node

![Untitled](Delete%20a%20given%20node%20in%20O(1)%20time%207bb9b384ec15419eb13c0cc03d8ea427/Untitled%201.png)