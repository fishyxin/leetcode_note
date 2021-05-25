# 剑指 Offer 03. 数组中重复的数字[简单]

[题目链接](https://leetcode-cn.com/problems/shu-zu-zhong-zhong-fu-de-shu-zi-lcof/)

## 解法

用一个map标记。

```go
func findRepeatNumber(nums []int) int {
    mark := make(map[int]bool)
    for _, n := range nums {
        if _, ok := mark[n]; ok {
            return n
        }
        mark[n] = true
    }
    return 0
}
```