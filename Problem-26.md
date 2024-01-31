## 84. Largest Area in Histogram

``` java
class Solution {
    public int largestRectangleArea(int[] heights) {
        int[]left=new int[heights.length];
        int[]right=new int[heights.length];
        Stack<Integer>stack=new Stack<>();
        // prev smaller to left
        for(int i=0;i<left.length;i++)
        {
            while(!stack.isEmpty()&&heights[stack.peek()]>=heights[i])
             stack.pop();
            left[i]=stack.isEmpty()?-1:stack.peek();
            stack.push(i);
        }stack.clear();
        // next smaller to left
        for(int i=left.length-1;i>=0;i--)
        {
            while(!stack.isEmpty()&&heights[stack.peek()]>=heights[i])
             stack.pop();
            right[i]=stack.isEmpty()?left.length:stack.peek();
            stack.push(i);
        }
        // cal max area
        int maxArea=0;
        for(int i=0;i<left.length;i++)
        {
            int area=heights[i]*(right[i]-left[i]-1);
            maxArea=Math.max(area,maxArea);
        }return maxArea;
    }
}
