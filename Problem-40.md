## 138. Copy List With Random Pointers

``` java
/*
// Definition for a Node.
class Node {
    int val;
    Node next;
    Node random;

    public Node(int val) {
        this.val = val;
        this.next = null;
        this.random = null;
    }
}
*/

class Solution {
    public Node copyRandomList(Node head) {
        if(head==null||head.next==null)return head;
        //make copy of the nodes between nodes
        Node temp=head;
        while(temp!=null)
        {
            Node newNode=new Node(temp.val);
            newNode.next=temp.next;
            temp.next=newNode;
            temp=temp.next.next;
        }
        //mark the random pointers
        temp=head;
        while(temp!=null)
        {
            if(temp.next!=null)
             temp.next.random=temp.random!=null?temp.random.next:null;
            temp=temp.next.next;
        }
        Node orig=head,copy=head.next;temp=copy;
        while(orig!=null)
        {
            orig.next=orig.next.next;
            copy.next=copy.next!=null?copy.next.next:copy.next;
            orig=orig.next;
            copy=copy.next;
        }return temp;
    }
}
