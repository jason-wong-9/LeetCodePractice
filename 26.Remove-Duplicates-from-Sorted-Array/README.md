#26. Remove Duplicates from Sorted Array
Given a sorted array, remove the duplicates in place such that each element appear only once and return the new length.
```java
public int removeDuplicates(int[] nums) {
    int length = nums.length;
    if (length < 2) return 2;
    int i = 1;
    for (int j = 1; j < length; ++j){
        if (nums[j] != nums[j-1])
            nums[i++] = nums[j];
    }
    return i;
}
```
