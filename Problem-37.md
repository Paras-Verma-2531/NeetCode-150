## 2. Add Two Numbers

```java
class Solution {
    public ListNode addTwoNumbers(ListNode l1, ListNode l2) {
        ListNode dummy=new ListNode(-1);
        ListNode temp=dummy;
        int carry=0;
        while(l1!=null||l2!=null)
        {
            int sum=l1==null?0:l1.val;
            l1=l1==null?null:l1.next;
            sum+=l2==null?0:l2.val;
            l2=l2==null?null:l2.next;
            sum+=carry;
            carry=sum/10;
            temp.next=new ListNode(sum%10);
            temp=temp.next;
        }
        if(carry>0)temp.next=new ListNode(carry);
        return dummy.next;
    }
}
