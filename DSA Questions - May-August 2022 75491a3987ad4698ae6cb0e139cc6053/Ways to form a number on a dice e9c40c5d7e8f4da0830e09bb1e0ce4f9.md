# Ways to form a number on a dice

## Approach

- Use the principle of inclusion and exclusion
- loop from 1 to 6
- call the function in each iteration with i added to the string and target - 1

## Base case

If the target is equal to 0 

print the string 

return

```java
public static void dice(String p,int target){
	    if(target == 0){
	        System.out.println(p);
	        return;
	    }
	    
	    for(int i=1;i<=6 && i<=target;i++){
	        dice(p+i,target-i);
	    }
	}
```

```java
public static ArrayList<String> dice(String p,int target){
	    if(target == 0){
	        ArrayList<String> list = new ArrayList<String>();
	        list.add(p);
	        return list;
	    }
	    
	    ArrayList<String> ret = new ArrayList<String>();
	    for(int i=1;i<=6 && i<=target;i++){
	        ret.addAll(dice(p+i,target-i));
	    }
	    return ret;
	}
```