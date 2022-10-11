# Path with obstacles

![Untitled](Path%20with%20obstacles%2092fdeb4ba6d846f198eb0a42bd3e161b/Untitled.png)

## Problem

We need to reach the last position of the matrix, if there is water in our path we need to take another path 

## Idea

We move RIGHT and DOWN like we normally do but, whenever we land on water we move out of the recursive call. We return to the previous call 

This will all be done in a boolean array 

```java
public static void main(String[] args) {
		boolean[][] list = {
		    {true,true,true},
		    {true,false,true},
		    {true,true,true}
		};
		List<String> harsh = new ArrayList<String>();
		harsh = path("",list,0,0);
		for(int i=0;i<harsh.size();i++){
		    System.out.println(harsh.get(i));
		}
 	}
	
	public static List<String> path(String p,boolean[][] maze,int r,int c){
	    if(r == maze.length - 1 && c == maze[0].length - 1){
	        List<String> path = new ArrayList<String>();
	        path.add(p);
	        return path;
	    }
	    
	    if(maze[r][c] == false){
	        List<String> n = new ArrayList<String>();
	        return n;
	    }
	    
	    List<String> res = new ArrayList<String>();
	    if(r < maze.length - 1){
	        res.addAll(path(p+'D',maze,r+1,c));    
	    }
	    
	    if(c < maze[0].length - 1){
	        res.addAll(path(p+'R',maze,r,c+1));    
	    }
	    
	    return res;
	}
```