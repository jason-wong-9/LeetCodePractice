#25. Reverse Nodes in K-Group
Given a linked list, reverse the nodes of a linked list k at a time and return its modified list. If the number of nodes is not a multiple of k then left-out nodes in the end should remain as it is.
```java
public ListNode reverseKGroup(ListNode head, int k) {
    ListNode curr = head;
    int count = 0;
    // Find the k + 1 node
    while (curr != null && count != k){
        curr = curr.next;
        count++;
    }
    if (count == k){
        curr = reverseKGroup(curr, k); // reverse list with k+1 node as head
        while (count -- > 0){
            ListNode tmp = head.next;
            head.next = curr;
            curr = head;
            head = tmp;
        }
        head = curr;
    }
    return head;
}
```
