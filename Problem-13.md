## 11. Container With Most Water

```java
class Solution {
    public int maxArea(int[] height) {
        int n=height.length;
        int low=0,high=n-1;
        int res=0;
        while(low<high)
        {
            int length=high-low;
            int area=Math.min(height[high],height[low])*length;
            res=Math.max(res,area);
            if(height[low]<height[high])low++;
            else high--;
        }return res;
    }
}
