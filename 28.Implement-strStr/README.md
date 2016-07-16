#28. Implement strStr()
Implement strStr() which returns the index of the first occurence of needle in haystack, or -1 if needle is not part of haystack.
```java
public int strStr(String haystack, String needle) {
    for (int i = 0; ;i++){
        for (int j = 0; ; j++){
            if (j == needle.length()) return i;
            if (i + j == haystack.length()) return -1;
            if (needle.charAt(j) != haystack.charAt(i+j)) break;
        }
    }
}
```
