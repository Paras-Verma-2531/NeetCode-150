# 572. Subtree of Another Tree
``` java
class Solution {
    private boolean isSameTree(TreeNode p,TreeNode q)
    {
        if(p==null||q==null)return p==q;
        boolean left=isSameTree(p.left,q.left);
        boolean right=isSameTree(p.right,q.right);
        return p.val==q.val&&left&&right;
    }
    public boolean isSubtree(TreeNode root, TreeNode subRoot) {
        if(root==null)return subRoot==null;
        boolean ans=isSameTree(root,subRoot);
        if(ans==true)return true;
        boolean left=isSubtree(root.left,subRoot);
        boolean right=isSubtree(root.right,subRoot);
        return left||right;
    }
}
