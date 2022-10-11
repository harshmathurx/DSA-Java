# Reverse Words in the String

# I trust you to understand this harsh

do not let me down

```java
public String reverseWords(String s) {
        String[] words = s.split(" +");
        StringBuilder res = new StringBuilder();
        
        for(int i=words.length-1;i>=0;i--){
            res.append(words[i]);
            res.append(" ");
        }
        return res.toString().trim();
    }
```