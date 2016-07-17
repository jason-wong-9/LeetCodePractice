#29. Divide Two Integers
Divide two integers without using multiplication, division and mod operator.
```java
public int divide(int dividend, int divisor) {
    if (divisor == 1) return dividend;
    if (divisor == 0 || (dividend == Integer.MIN_VALUE && divisor == -1))
        return Integer.MAX_VALUE;
    int sign = (((divisor < 0) ^ (dividend < 0)) ? -1 : 1);
    long dsor = Math.abs((long) divisor);
    long dend = Math.abs((long) dividend);
    long ans = 0;
    while (dend >= dsor){
        long temp = dsor;
        long helper = 1;
        //Multiplies the temp by 4, then increase by 1 afterwards
        while (dend > (temp << 2)){
            helper <<= 2;
            temp <<= 2;
        }
        dend -= temp;
        ans += helper;
    }
    return (int) (ans * sign);
}
```
