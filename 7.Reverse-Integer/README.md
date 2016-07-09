#7. Reverse Integer
Reverse digits of an integer.
```java
public int reverse(int x){
  boolean negative = false;
  //Using long instead of int to capture the Integer.MAX_VALUE
  long result = 0;
  if (x < 0){
    negative = true;
  }
  x = Math.abs(x);
  while (x > 0){
    result = 10 * result + (x % 10);
    x = x/10;
  }
  if (result > Integer.MAX_VALUE){
    return 0;
  }
  if (negative){
    result = -result;
  }
  return (int)result;
}
```
