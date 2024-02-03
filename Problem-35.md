## 19. Remove Nth Node From End

``` java
class Solution {
    public ListNode removeNthFromEnd(ListNode head, int n) {
        if(head==null||head.next==null)return null;
        ListNode newHead=new ListNode(-1,head);
       ListNode fast=newHead;ListNode slow=newHead;
        while(n--!=0)fast=fast.next;
        while(fast.next!=null)
         {
             slow=slow.next;
             fast=fast.next;
         }
         slow.next=slow.next.next;
        return newHead.next;
    }
}
