# Bottom View of Binary Tree

```java
		public class Pair {
			int hd;
			Node node;
				
			public Pair(Node _node, int _hd){
				this.node = _node;
				this.hd = _hd;
			}
		}
		
		static ArrayList<Integer> topView(Node root){
            ArrayList<Integer> ans = new ArrayList<>(); 
    
            if(root == null) return ans;
    
            Map<Integer, Integer> map = new TreeMap<>();
            Queue<Pair> q = new LinkedList<Pair>();
    
            q.add(new Pair(root, 0)); 
    
            while(!q.isEmpty()) {
                Pair it = q.remove();
                int hd = it.hd; 
                Node temp = it.node; 
    
                map.put(hd, temp.data); 
                
			    			if(temp.left != null) {
                    q.add(new Pair(temp.left, hd - 1)); 
                }
    
                if(temp.right != null) {
                    q.add(new Pair(temp.right, hd + 1)); 
                }
            }
        
            for (Map.Entry<Integer,Integer> entry : map.entrySet()) {
                ans.add(entry.getValue()); 
            }
            return ans; 
        }
```