# Sum of Nodes

![Untitled](Sum%20of%20Nodes%2096c8fdbb3c45498f9a0eeea4cccad44d/Untitled.png)

Almost the same as [Count No. of Nodes](Count%20No%20of%20Nodes%20ceab0fff8d7d4226b04494cb6ecca5ce.md) 

The only difference is that the formula changes

Sum of tree = Left subtree sum  + Right subtree sum + Root value 

```java
	public static int sumOfNodes(Node root){
        if(root == null){
            return 0;
        }

        int leftNodes = sumOfNodes(root.left);
        int rightNodes = sumOfNodes(root.right);

        return leftNodes + rightNodes + root.data;
	    }
```