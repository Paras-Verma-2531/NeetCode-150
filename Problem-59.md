# 90. Subsets II
```java
class Solution {
    private void subsetsWithDup(int[]arr,int ind,List<List<Integer>>ans,
    ArrayList<Integer>temp)
    {
        ans.add(new ArrayList<Integer>(temp));
        for(int i=ind;i<arr.length;i++)
        {
            if(i>ind&&arr[i]==arr[i-1])continue;
            temp.add(arr[i]);
            subsetsWithDup(arr,i+1,ans,temp);
            temp.remove(temp.size()-1);
        }
    }
    public List<List<Integer>> subsetsWithDup(int[] nums) {
        List<List<Integer>>ans=new ArrayList<>();
        Arrays.sort(nums);
        subsetsWithDup(nums,0,ans,new ArrayList<Integer>());
        return ans;
    }
}
