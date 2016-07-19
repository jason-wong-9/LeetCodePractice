#31 Next Permutation
Implement next permutation, which rearranges numbers into the lexicographically next greater permutation of numbers.
```java
public void nextPermutation(int[] nums) {
    for (int i = nums.length - 2, j = 0; i >= 0; i--){
        if(nums[i] < nums[i+1]){
            for (j = nums.length - 1; j > i; j--){
                if (nums[j] > nums[i]) break;
            }
            swap(nums, i, j);
            reverse(nums, i+1);
            return;
        } 
    }
    reverse(nums, 0);
}
public void swap(int[] nums, int i, int j){
    int tmp = nums[i];
    nums[i] = nums[j];
    nums[j] = tmp;
}
//reverse from start to end
public void reverse(int[] nums, int start){
    for( int i = start; i < (nums.length+start)/2;i++){
        swap(nums,i,start+nums.length-1-i);
    }
}
```
