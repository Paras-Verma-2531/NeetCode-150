## 23. Merge K Sorted Lists

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
    public ListNode mergeKLists(ListNode[] lists) {
        if(lists.length==0)return null;
        if(lists.length<2)return lists[0];
        PriorityQueue<Pair>pq=new PriorityQueue<>(new Comparator<Pair>()
        {
            public int compare(Pair a,Pair b)
            {
                return a.val-b.val;
            }
        });
        //insert into minHeap
        for(ListNode list:lists)
          if(list!=null)pq.offer(new Pair(list.val,list));
        ListNode dummy=new ListNode(-1);
        ListNode temp=dummy;
        while(!pq.isEmpty())
        {
            ListNode node=pq.poll().head;
            temp.next=node;
            temp=temp.next;
            if(node.next!=null)pq.offer(new Pair(
                node.next.val,node.next
            ));
            node.next=null;
        }return dummy.next;
        
    }
    class Pair
    {
        int val;
        ListNode head;
        public Pair(int val,ListNode head)
        {
            this.val=val;
            this.head=head;
        }
    }
}
