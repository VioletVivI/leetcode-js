# 剑指 Offer 25. 合并两个排序的链表

## 题目

https://leetcode-cn.com/problems/he-bing-liang-ge-pai-xu-de-lian-biao-lcof/

## 思路

迭代法。



## 解题

```javascript
/**
 * Definition for singly-linked list.
 * function ListNode(val) {
 *     this.val = val;
 *     this.next = null;
 * }
 */
/**
 * @param {ListNode} l1
 * @param {ListNode} l2
 * @return {ListNode}
 */
var mergeTwoLists = function(l1, l2) {
    if(l1 === null)return l2
    if(l2 === null)return l1
    // 迭代
    let cur = head = {val: 0, next: null} // 新建一个新节点
    while(l1 !== null && l2 !== null) {
        // l1 和 l2 进行对比，把小的拼接到新链表上
        if(l1.val < l2.val) {
            cur.next = l1
            l1 = l1.next
        }else {
            cur.next = l2
            l2 = l2.next
        }
         cur = cur.next
    }

    if(l1 === null){
        cur.next = l2
    }

    if(l2 === null) {
        cur.next = l1
    }
    return head.next
};
```