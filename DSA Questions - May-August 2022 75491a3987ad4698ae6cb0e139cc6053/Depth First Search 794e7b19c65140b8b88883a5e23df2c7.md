# Depth First Search

```java
public List<Integer> dfsGraph(List<List<Integer>> adj,int v){
	boolean[] vis = new boolean[v];
	ArrayList<Integer> dfs = new ArrayList<Integer>();
	dfs(0,vis,adj,dfs);
	return dfs;
}

public void dfs(int node,boolean[] vis,List<List<Integer>> adj,List<Integer> dfs){
	vis[node] = true;
	dfs.add(node);
	
	for(int x: adj.get(node)){
		if(!vis[x]){
			dfs(node,vis,adj,dfs);
		}
	}
}
```