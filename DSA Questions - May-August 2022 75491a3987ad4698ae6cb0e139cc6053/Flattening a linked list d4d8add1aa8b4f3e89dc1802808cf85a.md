# Flattening a linked list

[Flattening a Linked List | Practice | GeeksforGeeks](https://practice.geeksforgeeks.org/problems/flattening-a-linked-list/1)

[https://www.youtube.com/watch?v=ysytSSXpAI0&list=PLgUwDviBIf0p4ozDR_kJJkONnb1wdx2Ma&index=39](https://www.youtube.com/watch?v=ysytSSXpAI0&list=PLgUwDviBIf0p4ozDR_kJJkONnb1wdx2Ma&index=39)

```java
Node mergeLists(Node a,Node b){
        Node temp = new Node(0);
        Node res = temp;
        
        while(a != null && b!=null){
            if(a.data < b.data){
                temp.bottom = a;
                temp = temp.bottom;
                b = b.bottom;
            }
            else{
                temp.bottom = b;
                temp = temp.bottom;
                a = a.bottom;   
            }
        }
        
        if(a!= null){
            temp.bottom = a;
        }
        else{
            temp.bottom = b;
        }
        return res.next;
    }
    
    
    Node flatten(Node node)
    {
        if(node == null || node.next == null){
            return node;
        }
        
        node.next = flatten(node.next);
        
        node = mergeLists(node,node.next);
        
        return node;
    }
```