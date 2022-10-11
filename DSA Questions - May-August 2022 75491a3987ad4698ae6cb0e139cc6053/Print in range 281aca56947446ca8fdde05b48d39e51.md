# Print in range

We will be given an inclusive range [X,Y]

We need to print the nodes that lie in that given range

## Approach

There will be 3 case 

1. Root lies between X and Y
    
    recursive call for left subtree
    
    print root
    
    recursive call for right subtree
    
2. Root is greater than Y
    
    recursive call for the left subtree
    
3. Root is less than Y 
    1. recursive call for the right subtree

Base case

when root is null

return 

```java
		public void printInRange(Node root,int X,int Y){
        if(root == null){
            return;
        }
        
        if(root.data >= X && root.data <= Y){
            printInRange(root.left,X,Y);
            System.out.println(root.data,"");
            printInRange(root.right,X,Y);
        }
        
        else if(root.data >= Y){
            printInRange(root.left,X,Y);
        }
        
        else{
            printInRange(root.right,X,Y);
        }
    }
```