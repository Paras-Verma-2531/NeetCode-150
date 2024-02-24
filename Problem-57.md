# 39. Combination Sum
```java
class Solution {
    private void combinationSum(int[]arr,int ind,int sum,List<List<Integer>>ans,
    ArrayList<Integer>temp)
    {
        if(ind==arr.length)
        {
            if(sum==0)ans.add(new ArrayList<Integer>(temp));
            return;
        }
        if(sum>=arr[ind])
        {
            temp.add(arr[ind]);
            combinationSum(arr,ind,sum-arr[ind],ans,temp);
            temp.remove(temp.size()-1);
        }
        combinationSum(arr,ind+1,sum,ans,temp);
    }
    public List<List<Integer>> combinationSum(int[] candidates, int target) {
        List<List<Integer>>ans=new ArrayList<>();
        combinationSum(candidates,0,target,ans,new ArrayList<Integer>());
        return ans;
    }
}
