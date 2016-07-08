Given two linked lists representing two non-negative numbers. The digits are stored in reverse order and each of their nodes contain a single digit, add the two numbers and return it as a linked list.
```java
public ListNode addTwoNumbers(ListNode l1, ListNode l2){
  ListNode temp = new ListNode(0);
  ListNode p = l1, q = l2, curr = temp;
  int carry = 0;
  while (p != null || q != null){
    int x = (p != null) ? p.val : 0;
    int y = (q != null) ? q.val : 0;
    int sum = x + y + carry;
    carry = sum/10;
    curr.next = new ListNode(sum % 10);
    if (p != null){
      p = p.next;
    }
    if (q != null){
      q = q.next;
    }
    curr = curr.next;
  }
  if (carry > 0){
    curr.next = new ListNode(carry);
  }
  return temp.next;
}
```
