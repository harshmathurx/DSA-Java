# Phone pad problem

[Letter Combinations of a Phone Number - LeetCode](https://leetcode.com/problems/letter-combinations-of-a-phone-number)

## Approach

- Create an array of all possible strings on the number pad
- make a helper function with 3 parameters
    - input string
    - temp string
    - a variable to keep track of index
- In the helper function
    - base case - when the index is greater than or equal to the size of the input string
        - add the temp string to the list
        - return
    - small calculation:
        - Get the string of letters from the keys map
        - loop through the string
        - call the recursive helper function with the parameters
            - temp string + the char at index
            - input string
            - index + 1

```java
		private static final String[] KEYS = { "", "", "abc", "def", "ghi", "jkl", "mno", "pqrs", "tuv", "wxyz" };
	List<String> res = new LinkedList<String>();
    	
		public List<String> letterCombinations(String digits) {
	      if(digits.isEmpty() || digits.length() == 0) return res;

    		combination("", digits, 0);
    		return res;
    	}
    
    	private void combination(String prefix, String digits, int offset) {
    		if (offset >= digits.length()) {
    			res.add(prefix);
    			return;
    		}
    		String letters = KEYS[(digits.charAt(offset) - '0')];
    		for (int i = 0; i < letters.length(); i++) {
    			combination(prefix + letters.charAt(i), digits, offset + 1);
    		}
    	}
```