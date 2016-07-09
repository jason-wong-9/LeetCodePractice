#ZigZag Conversion
https://leetcode.com/problems/zigzag-conversion/

```java
public String convert(String s, int numRows){
  if (numRows <= 1) return s;
  StringBuilder builder = new StringBuilder();
  int cycle = 2 * numRows - 2;
  for (int i = 0; i < numRows; ++i){
    for (int j = i; j < s.length(); j = j + cycle){
      builder.append(s.charAt(j));
      int secondJ = (j - i) + cycle - i;
      if (i != 0 && i != numRows - 1 && secondJ < s.length())
        builder.append(s.charAt(secondJ));
    }
  }
  return builder.toString();
}
```
