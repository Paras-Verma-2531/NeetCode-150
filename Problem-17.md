## 424. Longest Repeating  Character Replacements

``` java
class Solution {
    public int characterReplacement(String s, int k) {
        int i=0,j=0;
        int maxLen=0,maxCount=0;
        Map<Character,Integer>map=new HashMap<>();
        while(j<s.length())
        {
            char ch=s.charAt(j);
            map.put(ch,map.getOrDefault(ch,0)+1);
            maxCount = Math.max(maxCount, map.get(ch));
            if ((j - i + 1 - maxCount) > k) {
                char leftChar = s.charAt(i);
                map.put(leftChar, map.get(leftChar) - 1);
                i++;
            }
            maxLen = Math.max(maxLen, j - i + 1);
            j++;
        }return maxLen;
    }
}
