#27. Remove Element
Given an array and a value, remove all instances of that value in place and return the new length.
```java
public int removeElement(int[] nums, int val) {
    int i = 0;
    int length = nums.length;
    if (length == 0) return 0;
    for (int j = 0; j < length; ++j){
        if (nums[j] != val){
            nums[i++] = nums[j];
        }
    }
    return i;
}
```
