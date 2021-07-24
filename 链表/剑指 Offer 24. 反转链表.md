# 剑指 Offer 24. 反转链表

## 题目

https://leetcode-cn.com/problems/fan-zhuan-lian-biao-lcof/

## 思路

方法一：迭代。

三个指针做标记，一步一步往前走，并进行翻转

方法二：递归。

类似二叉树的后续遍历，先找到最后一个节点，进行标记

再进行翻转：当前节点、后一个节点进行翻转。



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
 * @param {ListNode} head
 * @return {ListNode}
 */
var reverseList = function(head) {

    // 方法一：迭代
    // if(head == null) return null
    // let pre=null, cur=head, next=null;

    // while(cur != null) {
    //     next = cur.next
    //     cur.next = pre
    //     pre = cur
    //     cur = next
    // }
    // return pre

    // 方法二：递归
    const recur = (cur, pre) => {
        if(cur == null) return pre
        // res 就是最后一个节点，标记起来，这个就是反转后的头结点
        const res =  recur(cur.next, cur)
        cur.next = pre
        return res
    }
    return recur(head, null)
};
```



