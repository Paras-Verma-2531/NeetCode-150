## 20. Valid Parentheses

```java
class Solution {
    public boolean isValid(String s) {
        Stack<Character>stack=new Stack<>();
        for(int i=0;i<s.length();i++)
        {
            char ch=s.charAt(i);
            if(ch=='('||ch=='{'||ch=='[')stack.push(ch);
            else
            {
                if(stack.isEmpty())return false;
                char ch1=stack.peek();
                if(ch1=='('&&ch==')'||
                   ch1=='{'&&ch=='}'||
                   ch1=='['&&ch==']')stack.pop();
                else return false;
            }
        }return stack.isEmpty();
    }
}
