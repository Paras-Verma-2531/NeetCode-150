# 230. kth Smallest Element in a BST
```java
class Solution {
    private int kthSmallest(TreeNode root,int[]ind,int k)
    {
        if(root==null)return -1;
        int left=kthSmallest(root.left,ind,k);
        if(left!=-1)return left;
        ind[0]++;
        if(ind[0]==k)return root.val;
        return kthSmallest(root.right,ind,k);
    }
    public int kthSmallest(TreeNode root, int k) {
        return kthSmallest(root,new int[]{0},k);
    }
}
