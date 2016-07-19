#33. Search in Rotated Sorted Array
Suppose a sorted array is rotated at some pivot unknown to you beforehand. You are given a target value to search. If found in the array return its index, otherwise return -1.
```java
public int search(int[] nums, int target) {
    int n = nums.length;
    int lo = 0, hi = n-1;
    //Find index of smallest value using binary search.
    while (lo < hi){
        int mid = (lo+hi)/2;
        if (nums[mid] > nums[hi]) lo = mid+1;
        else hi = mid;
    }
    //rot = index of rotation
    int rot = lo;
    lo = 0; hi = n-1;
    while (lo <= hi){
        int mid = (lo+hi)/2;
        int realmid = (mid+rot)%n;
        if (nums[realmid] == target) return realmid;
        if (nums[realmid] < target) lo = mid+1;
        else hi = mid-1;
    }
    return -1;
}
```
