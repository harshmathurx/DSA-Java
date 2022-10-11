# Zig Zag Level Order Traversal

[Binary Tree Zigzag Level Order Traversal - LeetCode](https://leetcode.com/problems/binary-tree-zigzag-level-order-traversal)

## Approach

- Use normal level order traversal

[Tree Traversals](Tree%20Traversals%20c679cd44ef6340a3a1b40d2ec52446d9.md)

- Just reverse the order at every iteration
- For odd iterations
    - Go right to left
- For even iterations
    - Go left to right

## Explanation

- Keep a boolean variable called flag
- If the flag is true
    - Traverse left to right
    - else, right to left
- At every level iteration, reverse the flag using `flag = !flag`

```java
	public List<List<Integer>> zigzagLevelOrder(TreeNode root) {
        Queue <TreeNode> queue = new LinkedList <TreeNode> ();
        List<List<Integer>> wrapList = new ArrayList <> ();

        if (root == null) return wrapList;

        queue.offer(root);
        boolean flag = true;
        
        while (!queue.isEmpty()) {
            int levelNum = queue.size();
            ArrayList < Integer > subList = new ArrayList <Integer> (levelNum);
            for (int i = 0; i < levelNum; i++) {

                if (queue.peek().left != null) queue.offer(queue.peek().left);
                if (queue.peek().right != null) queue.offer(queue.peek().right);
                
                if (flag == true){
                    subList.add(queue.poll().val);
                }
                else{
                    subList.add(0, queue.poll().val);
                }
                
            }
            flag = !flag;
            wrapList.add(subList);
        }

        return wrapList;
	    }
```