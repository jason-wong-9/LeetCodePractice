#8. String to Integer (atoi)
Implement atoi to convert a string to an integer.
```java
public int myAtoi(String str){
  if (str.equals("")) return 0;
  int sign = 1, base = 0, i = 0;
  //skip through leading whitespace
  while (str.charAt(i) == ' '){
    i++;
  }
  // check signs whether there is a negative symbol
  if (str.charAt(i) == '-' || str.charAt(i) == '+')
    sign = str.charAt(i++) = '-' ? -1 : 1;
  
  while (i < str.length() && str.charAt(i) >= '0' && str.charAt(i) <= '9'){
    // deal with overflow
    if (base > Integer.MAX_VALUE / 10 || (base == Integer.MAX_VALUE / 10 && str.charAt(i) - '0' > 7)){
      return (sign == 1) ? Integer.MAX_VALUE : Integer.MIN_VALUE;
    }
    base = 10 * base + (str.charAt(i++) - '0');
  }
  return base * sign;
}
```
