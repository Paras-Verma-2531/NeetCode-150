# 46. Permutations
```java
class Solution {
    private void permute(int[]arr,boolean[]vis,List<List<Integer>>ans,ArrayList<Integer>temp)
    {
        if(temp.size()==arr.length)
        {
            ans.add(new ArrayList<Integer>(temp));
            return;
        }
       for(int i=0;i<arr.length;i++)
       {
           if(!vis[i])
           {
               vis[i]=true;
               temp.add(arr[i]);
               permute(arr,vis,ans,temp);
               vis[i]=false;
               temp.remove(temp.size()-1);
           }
       }
    }
    public List<List<Integer>> permute(int[] nums) {
        List<List<Integer>>ans=new ArrayList<>();
        permute(nums,new boolean[nums.length],ans,new ArrayList<Integer>());
        return ans;
    }
}
