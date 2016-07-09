Giveen a string S, find the longest palindromic substring in S. 
```java
public String longestpalindrome(String s){
  int length = s.length();
  int max = 1;
  int start = 0;
  boolean[][] table = new boolean[length][length];
  // Base Case 1: table[i][i] = true;
  for (int i = 0; i < length; ++i){
    table[i][i] = true;
  }
  // Base Case 2: table[i][i+1] = true if s.charAt(i) == s.charAt(i+1)
  for (int i = 0; i < length; ++i){
    if (s.charAt(i) == s.charAt(i+1)){
      start = i;
      max = 2;
      table[i][i+1] = true;
    }
  }
  for (int current_length = 3; current_length <= length; ++current_length){
    for (int i = 0; i < length - current_length + 1; ++i){
      int j = i + current_length - 1;
      if (table[i+1][j-1] && s.charAt(i) == s.charAt(j)){
        table[i][j] = true;
        max = current_length;
        start = i;
      }
    }
  }
  // [start, start+max)
  return s.substring(start, start + max);
}
```
