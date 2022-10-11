# Breadth-First Search

```java
public List<Integer> bfs(List<List<Integer>> adj, int v){
	ArrayList<Integer> bfs = new ArrayList<Integer>();
	boolean[] vis = new boolean[v];
	Queue<Integer> q = new LinkedList<Integer>();
	
	q.add(0);
	vis[0] = true;
	
	while(!q.isEmpty()){
		int node = q.poll();
		for(int x: adj.get(node)){
			if(!vis[x]){
				vis[x] = true;
				bfs.add(x);
			}
		}
		return bfs;
	}
}
```