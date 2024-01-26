## 36. Longest Consecutive Sequence

```java
 //Brute-force
/*
 for each ele find it's next
x=i+1 while present x++ and len++
cal maxLen
*/
class Solution {
    public int longestConsecutive(int[] nums) {
        if(nums.length==0)return 0;
        int maxLen=1;
        int len=1;
        Arrays.sort(nums);
        int prev=Integer.MIN_VALUE;
        for(int i:nums)
        {
            if(i==prev)continue;
            if(i==prev+1)
            {
                len++;
                prev=i;
            }else{len=1;prev=i;}
            maxLen=Math.max(maxLen,len);
        }return maxLen;
    }
}
