#Palindrome Number
Determine whether an integer is a palindrome.
```java
public boolean isPalindrome(int x){
  if (x == 0) return true;
  if (x < 0 || x % 10 == 0) return false;
  int v = 0;
  while (x > v){
    v = x % 10 + v * 10;
    x = x / 10;
  }
  return x == v || v / 10 == x;
}
```
