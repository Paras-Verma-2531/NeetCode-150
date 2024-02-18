# 199. Binary Tree Right Side View
```java
class Solution {
    public List<Integer> rightSideView(TreeNode root) {
        Map<Integer,Integer>map=new HashMap<>();
        Queue<TreeNode>q=new LinkedList<>();
        List<Integer>ans=new ArrayList<>();
        if(root==null)return ans;
        q.offer(root);
        int level=0;
        while(!q.isEmpty())
        {
           int size=q.size();
           for(int i=1;i<=size;i++)
           {
               TreeNode node=q.poll();
               map.put(level,node.val);
               if(node.left!=null)q.offer(node.left);
               if(node.right!=null)q.offer(node.right);
           }level++;
        }
        return new ArrayList<Integer>(map.values());
    }
}
