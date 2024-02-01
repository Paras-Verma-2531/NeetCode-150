## 153. Find Minimum in Rotated Sorted Array

``` java
class Solution {
    public int findMin(int[] nums) {
        int start=0,end=nums.length-1;
        int min=Integer.MAX_VALUE;
        while(start<=end)
        {
            int mid=(start+end)/2;
            if (nums[start]<=nums[mid])
            {
                min=Math.min(nums[start],min);
                start=mid+1;
            }
            else
            {
                min=Math.min(nums[mid],min);
                end=mid-1;
            }
        }return min;
    }
}
