## 11. Container With Most Water

```java
class Solution {
//brute-force: n^2
/*
  public int maxArea(int[] height) {
        int n=height.length;
        int res=0;
        for(int i=0;i<n;i++)
        {
            for(int j=i+1;j<n;j++)
            {
                int length=j-i;
                int area=length*Math.min(height[i],height[j]);
                res=Math.max(res,area);
            }
        }return res;
    }
*/
//optimal sol :: 2-pointers
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
