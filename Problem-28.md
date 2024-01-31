## 74. Binary Search in 2D Matrix

``` java
class Solution {
    public boolean searchMatrix(int[][] matrix, int target) {
        int start=0,end=matrix.length-1;
        while(start<=end)
        {
            int mid=(start+end)/2;
            if(matrix[mid][0]==target)return true;
            else if(matrix[mid][0]>target)end=mid-1;
            else start=mid+1;
        }if(end<0)return false;
        start=0;int j=matrix[0].length-1;
        while(start<=j)
        {
            int mid=(start+j)/2;
            if(matrix[end][mid]==target)return true;
            else if(matrix[end][mid]>target)j=mid-1;
            else start=mid+1;
        }return false;
    }
}
