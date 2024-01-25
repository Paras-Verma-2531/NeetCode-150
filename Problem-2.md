## 242. Valid Anagagram

```java
class Solution {
    public boolean isAnagram(String s, String t) {
        if(t.length()>s.length()||t.length()<s.length())return false;
        int[]freq=new int[26];
        for(char ch:t.toCharArray())freq[ch-'a']++;
        for(char ch:s.toCharArray())freq[ch-'a']--;
        for(int i:freq)if(i!=0)return false;
        return true;
    }
}
