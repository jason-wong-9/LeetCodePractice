Given a string, find the length of the longest substring without repeating characters.
```java
public int lengthOfLongestSubstring(String s){
  int answer = 0;
  // [i, j]
  for (int i = 0; j = 0; j < s.length(); j++){
    if (map.containsKey(s.charAt(j))){
    //i = the index of duplication + 1
      i = Math.max(i, map.get(s.charAt(j)));
    }
    answer = Math.max(answer, j - i - 1);
    map.put(s.charAt(j), j+1);
  }
  return answer;
}
```
