      /**
     * Definition for singly-linked list.
     * public class ListNode {
     *     int val;
     *     ListNode next;
     *     ListNode(int x) {
     *         val = x;
     *         next = null;
     *     }
     * }
     */
    public class Solution {
        public ListNode getIntersectionNode(ListNode headA, ListNode headB) {
            ListNode h1 = headA;
            ListNode h2 = headB;
            while(h1!=null && h2!=null){
                if(h1 == h2) return h1;
                if(h1.next!=null) h1 = h1.next;
                else {h1 = headB;headB= null;}

            if(h2.next!=null) h2 = h2.next;
            else {h2 = headA;headA=null;}
        }
        return null;
    }
}
