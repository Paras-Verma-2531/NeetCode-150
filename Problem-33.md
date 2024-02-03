## 21. Merge Two Sorted List

``` java
class Solution {
    public ListNode mergeTwoLists(ListNode list1, ListNode list2) {
        ListNode dummy=new ListNode(-1);
        ListNode temp=dummy;
        while(list1!=null&&list2!=null)
        {
            if(list1.val<list2.val)
            {
                temp.next=list1;
                list1=list1.next;
                temp=temp.next;
                temp.next=null;
            }
            else
            {
              temp.next=list2;
               list2=list2.next;
                temp=temp.next;
                temp.next=null;
            }
            
        }temp.next=list1!=null?list1:list2;
        return dummy.next;
    }
}
