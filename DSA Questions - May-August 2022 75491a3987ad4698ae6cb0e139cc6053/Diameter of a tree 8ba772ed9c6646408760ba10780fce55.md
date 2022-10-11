# Diameter of a tree

Diameter = Number of nodes in the longest path between 2 nodes 

**There can be 2 major cases**

Case 1: Going through Root

![Untitled](Diameter%20of%20a%20tree%208ba772ed9c6646408760ba10780fce55/Untitled.png)

Case 2: Diameter not going through the root 

![Untitled](Diameter%20of%20a%20tree%208ba772ed9c6646408760ba10780fce55/Untitled%201.png)

## Direct Approach

![Untitled](Diameter%20of%20a%20tree%208ba772ed9c6646408760ba10780fce55/Untitled%202.png)

Find the diameter for all 3 cases 

Return the max value 

![Untitled](Diameter%20of%20a%20tree%208ba772ed9c6646408760ba10780fce55/Untitled%203.png)

![Untitled](Diameter%20of%20a%20tree%208ba772ed9c6646408760ba10780fce55/Untitled%204.png)

In this case, the max diameter is going through the root

# Time Complexity - O(N^2)

Visiting every node - O(N)

Calculating 2 heights - O(N) + O(N) - approx O(N)

For every node, calculating the height - O(N * N)

```java
	public static int diameter(Node root){
        if(root == null){
            return 0;
        }

        int left = diameter(root.left);
        int right = diameter(root.right);
        int both = height(root.left) + height(root.right) + 1;

        return Math.max(Math.max(left,right),both);
    }
```

```java
	public static int height(Node root){
        if(root == null){
            return 0;
        }

        int leftHeight = height(root.left);
        int rightHeight = height(root.right);

				//choosing the deepest leaf
        return Math.max(leftHeight, rightHeight) + 1;
    }
```

## Optimized Approach

Time Complexity - O(N)

- We were calculating height at every recursive call
- We could have done that better

At every recursive call, we calculate the height and the diameter based on the left and right subtree’s height and diameter

- We don’t need to calculate the height for every node
- We can use the left and right node’s height and diameter by storing them in a class called tree info
- The function diam2 returns a TreeInfo object
- We can access the height and diameter of the root node by
    - `treeInfo.height`
    - `treeInfo.diameter`

For example - at every step we calculate the max height

Instead of calling the height function for the left and right node 

We will just use `left.height` and `right.height` 

This will we save O(N) time 

```java
		static class TreeInfo{
        int height;
        int diameter;

        TreeInfo(int ht,int diam){
            this.height = ht;
            this.diameter = diam;
        }
    }

    public static TreeInfo diameter2(Node root){

        if(root == null){
            return new TreeInfo(0,0);
        }

        TreeInfo left = diameter2(root.left);
        TreeInfo right = diameter2(root.right);

        int myHeight = Math.max(left.height, right.height) + 1;
        int diam1 = left.diameter;
        int diam2 = right.diameter;
        int diam3 = left.height + right.height + 1;

        int myDiam = Math.max(Math.max(diam1,diam2),diam3);
        TreeInfo myInfo = new TreeInfo(myHeight,myDiam);
        return myInfo;
    }
```