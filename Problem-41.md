## 25. Reverse Nodes in k Groups

```java
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
    private ListNode getKthNode(ListNode head,int k)
    {
        int count=0;ListNode temp=head;
        while(++count<k)
        {
            if(temp==null)break;
            temp=temp.next;
        }return temp;
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
    public ListNode reverseKGroup(ListNode head, int k) {
        if(head.next==null||k==1)return head;
        ListNode curr=head,prev=null;
        while(curr!=null)
        {
            ListNode kthNode=getKthNode(curr,k);
            if(kthNode==null)
            {
                prev.next=curr;
                break;
            }
            ListNode nextnode=kthNode.next;
            kthNode.next=null;
            ListNode newHead=reverse(curr);
            if(prev==null)head=newHead;
            else
            {
               prev.next=newHead;
            }prev=curr;
            curr=nextnode;
        }return head;
    }
}
