## 49. Group Anagram

```java
class Solution {
    public List<List<String>> groupAnagrams(String[] strs) {
        Map<String,List<String>>map=new HashMap<>();
        for(String str:strs)
        {
            char[]ch=str.toCharArray();
            Arrays.sort(ch);
            String s1=new String(ch);
            if(map.containsKey(s1))map.get(s1).add(str);
            else
            {
                map.put(s1,new ArrayList<String>());
                map.get(s1).add(str);
            }
        }return new ArrayList<>(map.values());
    }
}
