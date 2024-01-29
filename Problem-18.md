## 567. Permutations in String

``` java
class Solution {
    public boolean checkInclusion(String s1, String s2) {
        int i=0,j=0;
        Map<Character,Integer>map=new HashMap<>();
        Map<Character,Integer>map2=new HashMap<>();
        for(char ch:s1.toCharArray())
         map.put(ch,map.getOrDefault(ch,0)+1);
        int k=s1.length();
        while(j<s2.length())
        {
            char ch1=s2.charAt(j);
            map2.put(ch1,map2.getOrDefault(ch1,0)+1);
            if(j-i+1==k)
            {
                if(map.equals(map2))return true;
                char ch2=s2.charAt(i);
                map2.put(ch2,map2.get(ch2)-1);
                if(map2.get(ch2)==0)map2.remove(ch2);
                i++;
            }j++;
        }return false;
    }
}
