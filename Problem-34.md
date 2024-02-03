##  143. Reorder Lis

``` java
/**
 * Definition for singly-linked list.
 * public class ListNode {
 *     int val;
 *     ListNode next;
 *     ListNode() {}
 *     ListNode(int val) { this.val = val; }
 *     ListNode(int val, ListNode next) { this.val = val; this.next = next; }
 * }
 */
class Solution {
    private ListNode getMiddle(ListNode head)
    {
       ListNode slow=head,fast=head.next;
       while(fast!=null&&fast.next!=null)
       {
           fast=fast.next.next;
           slow=slow.next;
       }return slow;
    }
    private ListNode reverse(ListNode head)
    {
        ListNode curr=head,nextnode=null,prev=null;
        while(curr!=null)
        {
            nextnode=curr.next;
            curr.next=prev;
            prev=curr;
            curr=nextnode;
        }return prev;
    }
    public void reorderList(ListNode head) {
     if(head==null||head.next==null)return;
      ListNode middle=getMiddle(head);
      ListNode revHead=reverse(middle.next);
      middle.next=null;
      ListNode temp=head;
      while(temp!=null)
      {
        ListNode newtemp=temp.next;
        ListNode revtemp=revHead!=null?revHead.next:null;
        temp.next=revHead;
        if(revHead!=null)revHead.next=newtemp;
        temp=newtemp;
        revHead=revtemp;
      }
    }
}
