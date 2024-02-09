## 543. Diameter of Binary Tree

```java
class Solution {
    private int height(TreeNode root,int[]ans)
    {
        if(root==null)return 0;
        int lh=height(root.left,ans);
        int rh=height(root.right,ans);
        ans[0]=Math.max(ans[0],lh+rh);
        return 1+Math.max(lh,rh);
    }
    public int diameterOfBinaryTree(TreeNode root) {
        int[]ans={0};
        height(root,ans);
        return ans[0];
    }
}
