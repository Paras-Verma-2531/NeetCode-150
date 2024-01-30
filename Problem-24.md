## . Generate Parenthesis

``` java
class Solution {
    private void helper(List<String>res,int open,int close,int n,String s)
    {
        if(s.length()==2*n)
        {
            res.add(s);
            return;
        }
        if(open<n)
        {
            helper(res,open+1,close,n,s+"(");
        }
        if(open>close)
        {
            helper(res,open,close+1,n,s+")");
        }
    }
    public List<String> generateParenthesis(int n) {
        List<String>ans=new ArrayList<>();
        helper(ans,0,0,n,"");
        return ans;
    }
}
