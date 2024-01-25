## 217. Contains Duplicates

```java
class Solution {
    public boolean containsDuplicate(int[] nums) {
        //brute force:
        for(int i:nums)
        {
            int count=0;
            for(int j:nums)if(j==i)count++;
            if(count>1)return true;
        }return false;

        //better approach :: hashing||set
        Set<Integer>set=new HashSet<>();
        for(int i:nums)
        {
            if(set.contains(i))return true;
            set.add(i);
        }return false;
    }
}
