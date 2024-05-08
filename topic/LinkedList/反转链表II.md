### 2024.5.8 反转链表 II  https://leetcode.cn/problems/reverse-linked-list-ii/description/

---

### JS


---

### Java

```java
class Solution {
    public ListNode reverseBetween(ListNode head, int left, int right) {
        // 必须要创建一个新的链表，因为要交换第一个和第二个的话，需要以第0个为当前节点，第0个的next是第二个
        // 如果没有这个的话 .NEXT.NEXT就会有空指针
        ListNode h = new ListNode(0);
        h.next = head;

        ListNode l1 = h;
        ListNode l2 = h.next;
        //
        for (int i = 0; i < left - 1; i++) {
            l1 = l1.next;
            l2 = l2.next;
        }
        for (int i = 0; i < right-left; i++) {
            // 头插法，把他想成不是第一个需要交换的节点，更容易理解
            ListNode l = l2.next;
            l2.next = l2.next.next;
            l.next = l1.next;
            l1.next = l;
        }
        return head;
    }
}
```