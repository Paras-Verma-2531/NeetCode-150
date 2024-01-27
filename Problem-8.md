## 659. Encode and Decode Strings

``` java
public class Solution {
    /*
     * @param strs: a list of strings
     * @return: encodes a list of strings to a single string.
     */
    public String encode(List<String> strs) {
        // write your code here
        StringBuilder str=new StringBuilder();
        for(String st:strs)
        {
            str.append(st);
            str.append("#.#");
        }return str.toString();
    }

    /*
     * @param str: A string
     * @return: decodes a single string to a list of strings
     */
    public List<String> decode(String str) {
        // write your code here
        List<String>list=new ArrayList<>();
        String temp="";
        for(int i=0;i<str.length()-3;i++)
        {
            while(!patternMatches(str.substring(i,i+3)))
            {
                temp+=str.charAr(i);
                i++;
            }list.add(temp);
            i=i+3;
            temp="";
        }return list;
    }
}
