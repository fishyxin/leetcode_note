# 剑指 Offer 07. 重建二叉树[中等]

[题目链接](https://leetcode-cn.com/problems/zhong-jian-er-cha-shu-lcof/)

## 解法
利用二叉树前序遍历、中序遍历的性质，前序遍历第一个点为根节点，中序遍历根节点左边部分为左子树，右边部分为右子树，之后递归处理。

```go
func buildTree(preorder []int, inorder []int) *TreeNode {
    if len(preorder) == 0 || len(inorder) == 0 {
        return nil
    }
    root := preorder[0]
    idx := 0
    for i, val := range inorder {
        if val == root {
            idx = i
            break
        }
    }
    lp, rp := preorder[1:idx+1], preorder[idx+1:]
    li, ri := inorder[:idx], inorder[idx+1:]
    leftTree := buildTree(lp, li)
    rightTree := buildTree(rp, ri)
    return &TreeNode{Val: root, Left: leftTree, Right: rightTree}
}
```