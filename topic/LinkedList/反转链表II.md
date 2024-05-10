### 2024.5.8 反转链表 II  https://leetcode.cn/problems/reverse-linked-list-ii/description/

---

### JS

```js
var reverseBetween = function(head, left, right) {
    const preNode = new ListNode(0)
    preNode.next = head
    let g = preNode, p = preNode.next
    for(let i = 0; i < left - 1; i++) {
        g = g.next
        p  = p.next
    }
    // g节点是要移动的第一个节点的前一个节点  是不动的
    // p节点是要移动的第一个节点 不断的把它后边的节点往p前面移动
    for(let i =0; i < right-left; i++) {
        const removed = p.next
        p.next = p.next.next
        removed.next = g.next
        g.next = removed
    }
    return preNode.next
};
```

---

### Java
