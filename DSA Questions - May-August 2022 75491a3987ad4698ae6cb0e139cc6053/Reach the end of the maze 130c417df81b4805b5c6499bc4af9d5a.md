# Reach the end of the maze

This is the same as [Path to reach the end of the matrix](Path%20to%20reach%20the%20end%20of%20the%20matrix%2000d6b92f6ce4498fab2fccffdc9e694b.md) 

But the only change is that we can move in all directions this time 

## Problem

When you move in all directions, you visit the same cell multiple times and go into and infinite loop

The solution here is to make every cell you’ve already visited false;

The problem that arises again is that, if a cell is marked false. We don’t move ahead with that cell.

To solve this problem we use backtracking

## Backtracking Approach

- Every time you go through a cell of the matrix, mark it as false
- Before returning to the previous call, mark it as true

```java
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
	    
	    maze[r][c] = false;
	    
	    List<String> res = new ArrayList<String>();
	    if(r < maze.length - 1){
	        res.addAll(path(p+'D',maze,r+1,c));    
	    }
	    
	    if(r > 0){
	        res.addAll(path(p+'U',maze,r-1,c));
	    }
	    
	    if(c > 0){
	        res.addAll(path(p+'L',maze,r,c-1));
	    }
	    
	    if(c < maze[0].length - 1){
	        res.addAll(path(p+'R',maze,r,c+1));    
	    }
	    
	    maze[r][c] = true;
	    return res;
	}
```