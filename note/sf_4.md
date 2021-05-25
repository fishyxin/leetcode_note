# 剑指 Offer 04. 二维数组中的查找

[题目链接](https://leetcode-cn.com/problems/er-wei-shu-zu-zhong-de-cha-zhao-lcof/)


## 解法
利用两个方向递增的性质，从矩阵的左上角开始找，如果比target大，则在下一行进行查找，反之则在该行向前查找。列坐标不需要重置。
```go
func findNumberIn2DArray(matrix [][]int, target int) bool {
    if len(matrix) == 0 {
        return false
    }
    n, m := len(matrix), len(matrix[0])
    row, col := 0, m-1
    for row < n && col >= 0 {
        if matrix[row][col] == target {
            return true
        }
        if matrix[row][col] > target {
            col--
        } else {
            row++
        }
    }
    return false
}
```