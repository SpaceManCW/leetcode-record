### 2024.4.22 删除链表倒数第n个节点  https://leetcode.cn/problems/remove-nth-node-from-end-of-list/description/
---
### JS
```JS
/**
 * Definition for singly-linked list.
 * function ListNode(val, next) {
 *     this.val = (val===undefined ? 0 : val)
 *     this.next = (next===undefined ? null : next)
 * }
 */
/**
 * @param {ListNode} head
 * @param {number} n
 * @return {ListNode}
 */
var removeNthFromEnd = function(head, n) {
    let len = 0
    let cur = head
    while (cur) {
        cur = cur.next
        len++
    }
    if(n === len) {
        return head.next
    }
    if(n > len) {
        return head
    }
    cur = head
    let add = len - n - 1
    while (add) {
        cur = cur.next
        add--
    }
    cur.next = cur.next.next
    return head
};
```
**时间复杂度:** `O(n)`

**空间复杂度:** `O(1)`

---
### Java
