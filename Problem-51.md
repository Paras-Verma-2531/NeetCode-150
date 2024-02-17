# 102.  Binary Tree Level Order Traversal
```java
class Solution {
    public List<List<Integer>> levelOrder(TreeNode root) {
        List<List<Integer>>ans=new ArrayList<>();
        Queue<TreeNode>q=new LinkedList<>();
        if(root==null)return ans;
        q.offer(root);
        List<Integer>temp;
        while(!q.isEmpty())
        {
            temp=new ArrayList<>();
            int size=q.size();
            for(int i=1;i<=size;i++)
            {
                TreeNode node=q.poll();
                temp.add(node.val);
                if(node.left!=null)q.offer(node.left);
                if(node.right!=null)q.offer(node.right);
            }ans.add(new ArrayList<>(temp));
        }
        return ans;
    }
}
