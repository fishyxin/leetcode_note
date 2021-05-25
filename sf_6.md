# 剑指 Offer 06. 从尾到头打印链表

[题目链接](https://leetcode-cn.com/problems/cong-wei-dao-tou-da-yin-lian-biao-lcof/)


## 解法1
遍历两遍，顺序遍历一遍存为数组，再逆序遍历数组，时间O(n+n)，空间复杂度O(n+n)
```go
func reversePrint(head *ListNode) []int {
    var arr []int
    for head != nil {
        arr = append(arr, head.Val)
        head = head.Next
    }
    var ans []int
    for i := len(arr)-1; i >= 0; i-- {
        ans = append(ans, arr[i])
    }
    return ans
}
```

## 解法2
提到后入先出会想到栈，解法1修改一下即为栈的实现。这道题也可以用递归的做法，代码会比较简约
```go
func reversePrint(head *ListNode) []int {
    if head == nil {
        return nil
    }
    return append(reversePrint(head.Next), head.Val)
}

```
