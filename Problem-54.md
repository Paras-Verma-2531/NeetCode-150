## 1448. Count Good Nodes in Binary Tree

```java
class Solution {
    private boolean isPathGood(TreeNode root,TreeNode nroot)
    {
        if(root==null||root.val>nroot.val)return false;
        if(root==nroot)return true;
        boolean left=isPathGood(root.left,nroot);
        if(left==true)return true;
        return isPathGood(root.right,nroot);
    }
    private void countGoodNodes(TreeNode root,TreeNode tempRoot,int[]ans)
    {
        if(tempRoot==null)return;
        if(isPathGood(root,tempRoot))ans[0]++;
        countGoodNodes(root,tempRoot.left,ans);
        countGoodNodes(root,tempRoot.right,ans);
    }
    public int goodNodes(TreeNode root) {
        int ans[]={0};
        countGoodNodes(root,root,ans);
        return ans[0];
    }
}
