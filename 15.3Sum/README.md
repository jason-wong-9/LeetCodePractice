#15. 3 Sum
Given an array S of n integers, are there elements a, b, c in S such that a + b + c = 0? Find all unique triplets in the array which give the sum of zero.
```java
public List<List<Integer>> threeSum(int[] nums) {
    Arrays.sort(nums);
    List<List<Integer>> res = new LinkedList();
    for (int i = 0; i < nums.length - 2; i++){
    //nums[i] would be one of the number, then use 2 sum method
        if (i == 0 || (i > 0 && nums[i] != nums[i-1])){
            int lo = i + 1, hi = nums.length - 1, sum = 0 - nums[i];
            while (lo < hi){
                if (nums[lo] + nums[hi] == sum){
                    res.add(Arrays.asList(nums[i], nums[lo], nums[hi]));
                    // Unique triplets
                    while (lo < hi && nums[lo] == nums[lo+1]) lo++;
                    while (lo < hi && nums[hi] == nums[hi-1]) hi--;
                    lo++; hi--;
                } else if (nums[lo] + nums[hi] < sum) lo++;
                else hi --;
            }
        }
    }
    return res;
}
```
