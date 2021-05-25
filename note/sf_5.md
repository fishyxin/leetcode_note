# 剑指 Offer 05. 替换空格[简单]

[题目链接](https://leetcode-cn.com/problems/ti-huan-kong-ge-lcof/)

## 解法
遍历一边即可
```go
func replaceSpace(s string) string {
    var ans []rune
    for _, c := range s {
        if c == ' ' {
            ans = append(ans, []rune{'%', '2', '0'}...)
        } else {
            ans = append(ans, c)
        }
    }
    return string(ans)
}
```