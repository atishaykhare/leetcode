# [1290. 二进制链表转整数](https://leetcode-cn.com/problems/convert-binary-number-in-a-linked-list-to-integer)

[English Version](/solution/1200-1299/1290.Convert%20Binary%20Number%20in%20a%20Linked%20List%20to%20Integer/README_EN.md)

## 题目描述

<!-- 这里写题目描述 -->

<p>给你一个单链表的引用结点&nbsp;<code>head</code>。链表中每个结点的值不是 0 就是 1。已知此链表是一个整数数字的二进制表示形式。</p>

<p>请你返回该链表所表示数字的 <strong>十进制值</strong> 。</p>

<p>&nbsp;</p>

<p><strong>示例 1：</strong></p>

<p><img alt="" src="https://cdn.jsdelivr.net/gh/doocs/leetcode@main/solution/1200-1299/1290.Convert%20Binary%20Number%20in%20a%20Linked%20List%20to%20Integer/images/graph-1.png" style="height: 108px; width: 426px;"></p>

<pre><strong>输入：</strong>head = [1,0,1]
<strong>输出：</strong>5
<strong>解释：</strong>二进制数 (101) 转化为十进制数 (5)
</pre>

<p><strong>示例 2：</strong></p>

<pre><strong>输入：</strong>head = [0]
<strong>输出：</strong>0
</pre>

<p><strong>示例 3：</strong></p>

<pre><strong>输入：</strong>head = [1]
<strong>输出：</strong>1
</pre>

<p><strong>示例 4：</strong></p>

<pre><strong>输入：</strong>head = [1,0,0,1,0,0,1,1,1,0,0,0,0,0,0]
<strong>输出：</strong>18880
</pre>

<p><strong>示例 5：</strong></p>

<pre><strong>输入：</strong>head = [0,0]
<strong>输出：</strong>0
</pre>

<p>&nbsp;</p>

<p><strong>提示：</strong></p>

<ul>
	<li>链表不为空。</li>
	<li>链表的结点总数不超过&nbsp;<code>30</code>。</li>
	<li>每个结点的值不是&nbsp;<code>0</code> 就是 <code>1</code>。</li>
</ul>

## 解法

<!-- 这里可写通用的实现逻辑 -->

先求链表长度 n，再遍历链表，累加求得结果。

<!-- tabs:start -->

### **Python3**

<!-- 这里可写当前语言的特殊实现逻辑 -->

```python
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, x):
#         self.val = x
#         self.next = None

class Solution:
    def getDecimalValue(self, head: ListNode) -> int:
        n, cur = 0, head
        while cur:
            n += 1
            cur = cur.next
        res, cur = 0, head
        while cur:
            n -= 1
            if cur.val == 1:
                res += (2 ** (n))
            cur = cur.next
        return res
```

### **Java**

<!-- 这里可写当前语言的特殊实现逻辑 -->

```java
/**
 * Definition for singly-linked list.
 * public class ListNode {
 *     int val;
 *     ListNode next;
 *     ListNode(int x) { val = x; }
 * }
 */
class Solution {
    public int getDecimalValue(ListNode head) {
        int n = 0;
        for (ListNode cur = head; cur != null; cur = cur.next) {
            ++n;
        }
        int res = 0;
        for (ListNode cur = head; cur != null; cur = cur.next) {
            --n;
            if (cur.val == 1) {
                res += Math.pow(2, n);
            }
        }
        return res;
    }
}
```

### **...**

```

```

<!-- tabs:end -->
