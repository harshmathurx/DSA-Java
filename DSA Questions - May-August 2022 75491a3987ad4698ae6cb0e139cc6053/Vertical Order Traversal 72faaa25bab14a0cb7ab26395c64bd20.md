# Vertical Order Traversal

```java
		public class Pair {
        int hd;
        TreeNode node;
        
        public Pair(int hd,TreeNode node){
            this.node = node;
            this.hd = hd;
        }
    }

    public List<List<Integer>> verticalTraversal(TreeNode root) {
        Queue <Pair> q = new LinkedList<Pair>();
        q.offer(new Pair(0,root));
        Map<Integer,ArrayList<Integer>> map = new TreeMap();
        while (!q.isEmpty()) {
            Pair curr = q.poll();
            if(map.containsKey(curr.hd)){
                map.get(curr.hd).add(curr.node.val);
            }
            else{
                ArrayList<Integer> temp = new ArrayList<>();
                temp.add(curr.node.val);
                map.put(curr.hd,temp);
            }
            
            if(curr.node.left != null){
                q.add(new Pair(curr.hd-1,curr.node.left));
            }
            
            if(curr.node.right != null){
                q.add(new Pair(curr.hd+1,curr.node.right));
            }
        }
        
        List<List<Integer>> ans = new ArrayList<>();
        for(Map.Entry<Integer,ArrayList<Integer>> entry: map.entrySet()){
            ans.add(entry.getValue());
        }
        return ans;
	    }
```