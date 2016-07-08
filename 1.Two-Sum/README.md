#Two Sum
Given an array of integers, return indices of the two numbers such that they add up to a specific target. You may assume that each input would have exactly one solution.

```java
public int[] twoSum(int[] nums, int target){
  HashMap<Integer, Integer> map = new HashMap();
  int[] sol = new int[2];
  for (int i = 0; i < nums.length; ++i){
    if (!map.containsKey(target - nums[i])){
      map.put(nums[i], i);
    } else {
      sol[0] = map.get(target-nums[i]);
      sol[1] = i;
      return sol;
    }
  }
  return sol;
}
```
