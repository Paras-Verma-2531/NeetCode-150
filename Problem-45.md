## 104. Maximum Depth of Binary Tree

```java
class Solution {
    public int maxDepth(TreeNode root) {
        if(root==null)return 0;
        int leftH=maxDepth(root.left);
        int rightH=maxDepth(root.right);
        return Math.max(leftH,rightH)+1;
    }
}
