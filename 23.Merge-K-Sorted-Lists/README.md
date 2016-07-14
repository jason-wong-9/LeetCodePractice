#23. Merge K Sorted Lists
Merge k sorted linked lists and return it as one sorted list.
```java
public ListNode mergeKLists(ListNode[] lists) {
    if (lists == null || lists.length == 0) return null;
    PriorityQueue<ListNode> queue = new PriorityQueue(lists.length, new Comparator<ListNode>(){
        
        @Override
        public int compare(ListNode o1, ListNode o2){
            if (o1.val < o2.val)
                return -1;
            else if (o1.val == o2.val)
                return 0;
            else 
                return 1;
        }
    });
    
    ListNode dummy = new ListNode(0);
    ListNode tail = dummy;
    for (ListNode node :lists){
        if (node != null){
            queue.add(node);
        }
    }
    while (!queue.isEmpty()){
        //Retrieve the next head of the priority queue
        tail.next = queue.poll();
        tail = tail.next;
        // After retrieving, add the next listnode of that list into the queue.
        if (tail.next != null)
            queue.add(tail.next);
    }
    return dummy.next;
}
```
