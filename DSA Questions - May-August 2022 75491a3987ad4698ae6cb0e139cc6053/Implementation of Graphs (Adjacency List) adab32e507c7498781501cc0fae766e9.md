# Implementation of Graphs (Adjacency List)

```java
public static class Graph<Integer>{
		private final Map<Integer, List<Integer> > map = new HashMap<>();
}
```

```java
		public void addNewVertex(Integer s)
		{
			map.put(s, new LinkedList<Integer>());
		}
```

```java
		public void addNewEdge(Integer source, Integer destination, boolean bidirectional)
		{
			if (!map.containsKey(source))
				addNewVertex(source);
			if (!map.containsKey(destination))
				addNewVertex(destination);

			map.get(source).add(destination);

			if (bidirectional == true)
			{
				map.get(destination).add(source);
			}

		}
```

```java
		//the method counts the number of vertices
		public void countVertices()
		{
			System.out.println("Total number of vertices: "+ map.keySet().size());
		}
```

```java
//the method counts the number of edges
		public void countEdges(boolean bidirection)
		{
			int count = 0;
			for (Integer v : map.keySet())
			{
				count = count + map.get(v).size();
			}
			if (bidirection == true)
			{
				count = count / 2;
			}
			System.out.println("Total number of edges: "+ count);
		}

```

```java
		public boolean containsVertex(Integer s)
		{
				return map.containsKey(s);
		}

		public boolean containsEdge(Integer s, Integer d)
		{
			return (map.get(s).contains(d));
		}
```