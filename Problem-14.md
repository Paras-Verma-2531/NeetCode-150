## 42. Trapping Rain Water

```java
class Solution {
    public int trap(int[] height) {
        int n=height.length;
        int[]leftHeight=new int[n];
        int[]rightHeight=new int[n];
        int max=0;
        for(int i=0;i<n;i++)
        {
            if(height[i]>max)max=height[i];
            leftHeight[i]=max;
        }
        //right max height
        max=0;
        for(int i=n-1;i>=0;i--)
        {
           if(height[i]>max)max=height[i];
           rightHeight[i]=max;
        }
        int sum=0;
        for(int i=0;i<n;i++)
        {
            sum+=Math.min(leftHeight[i],rightHeight[i])-height[i];
        }return sum;
    }
}
