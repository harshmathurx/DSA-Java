# Root to leaf path

![Untitled](Root%20to%20leaf%20path%209b55fe88a8174a3f80e4f42bf5697b28/Untitled.png)

```java
		public void rootToLeaf(Node root, List<Integer> path){
        if(root == null) return;
        
        path.add(root.data);
        
        if(root.left == null && root.right == null){
            printPath(root);
        }
        else{
            rootToLeaf(root.left,path);
            rootToLeaf(root.right,path);
        }

        path.remove(path.size()-1);
    }
```