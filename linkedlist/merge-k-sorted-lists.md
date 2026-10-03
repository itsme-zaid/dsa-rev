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
            if(lists.length == 0) return null;
            // merge k sorted lists;
            // 1 -> 1 -> 
            // 
            // 4 5 , 3 4 , 6
            // [ 1 -> 1 -> 2-> [] 4 5 ] [3 4] [ 2 6];
            PriorityQueue<ListNode> pq = new PriorityQueue<>((a,b) -> a.val - b.val);

        for( ListNode list : lists){
            if(list!=null) pq.add(list);
        }

        ListNode dummy = new ListNode(0);
        ListNode current = dummy;
        while(!pq.isEmpty()){
            ListNode small = pq.poll();

            current.next = small;
            current = current.next;
            if(small.next!=null){
                pq.add(small.next);
            }
        }
        return dummy.next;
    }
      }

## tried this cause wasnt really interested in finding another solution and looks like this is the optimal version;
