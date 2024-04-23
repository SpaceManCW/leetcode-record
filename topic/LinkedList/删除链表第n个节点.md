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

**双指针解法:**

```js
var removeNthFromEnd = function(head, n) {
    let dummy = new ListNode(0);
    dummy.next = head;
    let first = dummy;
    let second = dummy;
    for(let i=0; i<=n; i++) {
        first = first.next
    }
    while(first) {
        first = first.next
        second = second.next
    }
    second.next = second.next.next
    return dummy.next
};
```

注意尽量创建空节点连接头节点，如果n等于链表长度，for循环结束可能first直接为null，注意是循环了n+1次，当快节点指向null的时候，慢节点正好在待删除节点前一个节点

---

### Java
> 注意第二个while循环的截止条件，还有删除第一个节点的边界问题
```text
            ListNode l = head;
            ListNode l2 = head;
            if (n <= 0) return head;
            for (int i = 0; i < n; i++) {
                if (l == null) {
                    return head;
                }
                l = l.next;
            }
        if (l == null) return head.next;
            while (l.next != null)   {
                l = l.next;
                l2 = l2.next;
            }
            l2.next = l2.next.next;
            return head;
```