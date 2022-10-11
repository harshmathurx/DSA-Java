# Top View of Binary Tree

![Untitled](Top%20View%20of%20Binary%20Tree%20bba1b2e2575b4687bcd6c50fd4172b2a/Untitled.png)

**Intuition**
We can mark straight lines like in the image below and mark them with +ve and -ve indexes. The first node of every line will be my top view.

- Create a Pair class to store level and node at the level

![image-1663085671195.jpg5828094756175809519.jpg](Top%20View%20of%20Binary%20Tree%20bba1b2e2575b4687bcd6c50fd4172b2a/image-1663085671195.jpg5828094756175809519.jpg)

![Untitled](Top%20View%20of%20Binary%20Tree%20bba1b2e2575b4687bcd6c50fd4172b2a/Untitled%201.png)

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

            if(map.get(hd) == null) map.put(hd, temp.data); 
            
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