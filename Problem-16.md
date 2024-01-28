## 3. Longest Substring Without Repeating Characters

```java
class Solution {
    public int lengthOfLongestSubstring(String s) {
        int maxLen=0,prev=0;
        Set<Character>set=new HashSet<>();
        for(int i=0;i<s.length();i++)
        {
            while(set.contains(s.charAt(i)))
            {
                set.remove(s.charAt(prev));
                prev++;
            }set.add(s.charAt(i));
            maxLen=Math.max(maxLen,set.size());
        }return maxLen;
    }
}
