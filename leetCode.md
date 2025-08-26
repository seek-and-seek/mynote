class Solution {

  public int removeElement(int[] nums, int val) {

​    int i = -1;

​    int j = nums.length+1;

​    while(i<j){

​    do{ i++;}while(nums[i]!=val);

​    do{ j--;}while(nums[i]==val);

​    nums[i] = nums[j];

​    }

​    return j;

  }

}