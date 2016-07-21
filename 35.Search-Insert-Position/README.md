#35. Search Insert Position
Given a sorted array and a target value, return the index if that target it found. If not, return the index where it would be if it were inserted in order.
```java
public int searchInsert(int[] nums, int target) {
    return binarySearch(nums, target, 0, nums.length-1);
}
private int binarySearch(int[] nums, int target, int start, int end){
    
    while (start < end){
        int mid = (start + end)/2;
        if (target < nums[mid]){
            end = mid;
        }
        if (target > nums[mid]){
            start = mid + 1;
        }
        if (target == nums[mid]){
            return mid;
        }
    }

    return target <= nums[start] ? start : start + 1;
}
```
