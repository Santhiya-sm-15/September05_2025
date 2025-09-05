# September05_2025
The problem that I solved today

Given the head of a linked list where nodes can contain values 0s, 1s, and 2s only. Your task is to rearrange the list so that all 0s appear at the beginning, followed by all 1s, and all 2s are placed at the end.

Code:
class Solution {
    public Node segregate(Node head) {
        Node zero=null,z=null;
        Node one=null,o=null;
        Node two=null,t=null;
        for(Node i=head;i!=null;)
        {
            Node nxt=i.next;
            if(i.data==0)
            {
                if(zero==null)
                {
                    zero=i;
                    z=i;
                    z.next=null;
                }
                else
                {
                    z.next=i;
                    z=i;
                }
            }
            else if(i.data==1)
            {
                if(one==null)
                {
                    one=i;
                    o=i;
                    o.next=null;
                }
                else
                {
                    o.next=i;
                    o=i;
                }
            }
            else
            {
                if(two==null)
                {
                    two=i;
                    t=i;
                    t.next=null;
                }
                else
                {
                    t.next=i;
                    t=i;
                }
            }
            i.next=null;
            i=nxt;
        }
        head=null;
        if(zero!=null)
        {
            head=zero;
            z.next=one;
            if(one!=null)
                o.next=two;
            else
                z.next=two;
        }
        else if(one!=null)
        {
            head=one;
            o.next=two;
        }
        else
            head=two;
        return head;
    }
}
