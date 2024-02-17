## 110. Balanced Binary Tree

```java
class Solution {
    private int height(TreeNode root,boolean[]ans)
    {
        if(root==null)return 0;
        int lh=height(root.left,ans);
        int rh=height(root.right,ans);
        ans[0]=ans[0]&&Math.abs(lh-rh)<=1;
        return 1+Math.max(lh,rh);
    }
    public boolean isBalanced(TreeNode root) {
        if(root==null)return true;
        boolean[]ans={true};
        height(root,ans);
        return ans[0];
    }
}
