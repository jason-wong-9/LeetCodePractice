#10. Regular Expression Matching
Implement regular expression matching with support for '.' and '*'
```java
public boolean isMatch(String s, String p){
  boolean[][] table = new boolean[s.length() + 1][p.length() + 1];
  table[0][0] = true;
  //Deal with patterns like a* or a*b* or a*b*c*
  for (int i = 1; i < table[0].length; i++){
    if (p.charAt(i-1) == '*'){
      table[0][i] = table[0][i-2];
    }
  }
  for (int i = 1; i < table.length; i++){
    for (int j = 1; j < table[0].length; j++){
      if (p.charAt(j-1) == '.' || p.charAt(j-1) == s.charAt(i-1)){
        table[i][j] = table[i-1][j-1];
      } else if (p.charAt(j-1) == '*'){
        table[i][j] = table[i][j-2];
        if (p.charAt(j-2) == '.' || p.charAt(j-2) == s.charAt(i-1)){
          table[i][j] = table[i][j] | table[i-1][j];
        }
      } else {
        table[i][j] = false;
      }
    }
  }
  return table[s.length()][p.length()];
}
```
