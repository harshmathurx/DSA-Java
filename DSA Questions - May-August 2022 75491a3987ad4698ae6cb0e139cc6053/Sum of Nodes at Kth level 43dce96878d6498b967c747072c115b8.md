# Sum of Nodes at Kth level

![Untitled](Sum%20of%20Nodes%20at%20Kth%20level%2043dce96878d6498b967c747072c115b8/Untitled.png)

## Approach

- We use normal level order traversal

[Tree Traversals](Tree%20Traversals%20c679cd44ef6340a3a1b40d2ec52446d9.md)

- We have to use an extra variable to track the level we are on
- When we reach the kth level, we calculate the sum

[https://youtu.be/vQIiUWofWw8?t=449](https://youtu.be/vQIiUWofWw8?t=449)

```java

	public int sumAtKLevel(Node root, int k){
	    if(root == null){
	        return -1;
	    }
	    
	    Queue<Node> q = new LinkedList<Node>();
	    int sum = 0;
	    int level = 0;
	    
	    q.offer(root);
	    q.offer(null);
	    
	    while(!q.isEmpty()){
	        Node node = q.poll();
	        
	        if(node != null){
	            if(level == k){
	                sum += node.data;
	            }
	            
	            if(node.left != null){
	                q.offer(node.left);
	            }
	            
	            if(node.right != null){
	                q.offer(node.right);
	            }
	        }
	        
	        else if(!q.isEmpty()){
	            q.offer(null);
	            level++;
	        }
	    }
	    return sum;
	}
```