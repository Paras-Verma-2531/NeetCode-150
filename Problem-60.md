# 40. Combination Sum II
```java
class Solution {
    private void combinationSum(int[]arr,int ind,
    int sum,List<List<Integer>>ans,ArrayList<Integer>temp)
    {
        if(sum==0)
        {
            ans.add(new ArrayList<Integer>(temp));
            return;
        }
        for(int i=ind;i<arr.length;i++)
        {
            if(i>ind&&arr[i]==arr[i-1])continue;
            if(arr[i]>sum)break;
            temp.add(arr[i]);
            combinationSum(arr,i+1,sum-arr[i],ans,
            temp);
            temp.remove(temp.size()-1);
        }
    }
    public List<List<Integer>> combinationSum2(
        int[] candidates, int target) {
        List<List<Integer>>ans=new ArrayList<>();
        Arrays.sort(candidates);
        combinationSum(candidates,0,target,ans,
        new ArrayList<Integer>());
        return ans;
    }
}
