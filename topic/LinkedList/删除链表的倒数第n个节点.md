### 2024.5.23  删除链表的倒数第n个节点 https://leetcode.cn/problems/remove-nth-node-from-end-of-list/description/

---

### JS

```js
var removeNthFromEnd = function(head, n) {
    if(!head) return []
    let len = 0
    let node = head
    // 算出长度
    while(node) {
        node = node.next
        len++
    }
    let m = len - n + 1
    let pre = new ListNode(0)
    pre.next = head
    let res = pre
    for(let i = 1; i <= len; i++) {
        if(i===m) {
            pre.next = pre.next.next
            return res.next
        } else {
            pre = pre.next
        }
    }
};
```

---

### Java
```java
class Solution {
    public ListNode removeNthFromEnd(ListNode head, int n) {
            ListNode h = head;
            ListNode h2 = new ListNode(0);
            ListNode res = h2;
            h2.next = head;
            for (int i = 0; i < n; i++) {
                h = h.next;
            }
            while (h != null) {
                h = h.next;
                h2 = h2.next;
            }
            h2.next = h2.next.next;
            return res.next;
        }
}
```