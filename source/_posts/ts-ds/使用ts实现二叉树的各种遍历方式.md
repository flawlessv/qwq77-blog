---
title: 使用ts实现二叉树的各种遍历方式
cover: "https://www.dmoe.cc/random.php"
tags:
  - TypeScript
  - 二叉树
categories:
  - 数据结构
---

### 前序遍历
```ts
// 
function preorderTraversal(root: TreeNode | null): number[] {
    function traverse(root: TreeNode | null, res: number[]): void {
        if (root === null) return;
        res.push(root.val);
        traverse(root.left, res);
        traverse(root.right, res);
    }
    const res: number[] = [];
    traverse(root, res);
    return res;
}
```

### 中序遍历

```ts
function inorderTraversal(root: TreeNode | null): number[] {
    function traverse(root: TreeNode | null, res: number[]): void {
        if (root === null) return;
        traverse(root.left, res);
        res.push(root.val);
        traverse(root.right, res);
    }
    const res: number[] = [];
    traverse(root, res);
    return res;
}
```
### 后序遍历

```ts
function postorderTraversal(root: TreeNode | null): number[] {
    function traverse(root: TreeNode | null, res: number[]): void {
        if (root === null) return;
        traverse(root.left, res);
        traverse(root.right, res);
        res.push(root.val);
    }
    const res: number[] = [];
    traverse(root, res);
    return res;
}
```

### 迭代法
```ts
// 前序遍历（迭代法）
function preorderTraversal(root: TreeNode | null): number[] {
    if (root === null) return [];
    let res: number[] = [];
    let helperStack: TreeNode[] = [];
    let curNode: TreeNode = root;
    helperStack.push(curNode);
    while (helperStack.length > 0) {
        curNode = helperStack.pop()!;
        res.push(curNode.val);
        if (curNode.right !== null) helperStack.push(curNode.right);
        if (curNode.left !== null) helperStack.push(curNode.left);
    }
    return res;
};

// 中序遍历（迭代法）
function inorderTraversal(root: TreeNode | null): number[] {
    let helperStack: TreeNode[] = [];
    let res: number[] = [];
    if (root === null) return res;
    let curNode: TreeNode | null = root;
    while (curNode !== null || helperStack.length > 0) {
        if (curNode !== null) {
            helperStack.push(curNode);
            curNode = curNode.left;
        } else {
            curNode = helperStack.pop()!;
            res.push(curNode.val);
            curNode = curNode.right;
        }
    }
    return res;
};

// 后序遍历（迭代法）
function postorderTraversal(root: TreeNode | null): number[] {
    let helperStack: TreeNode[] = [];
    let res: number[] = [];
    let curNode: TreeNode;
    if (root === null) return res;
    helperStack.push(root);
    while (helperStack.length > 0) {
        curNode = helperStack.pop()!;
        res.push(curNode.val);
        if (curNode.left !== null) helperStack.push(curNode.left);
        if (curNode.right !== null) helperStack.push(curNode.right);
    }
    return res.reverse();
};
```
### 层序遍历
```ts
function levelOrder(root: TreeNode | null): number[][] {
    let helperQueue: TreeNode[] = [];
    let res: number[][] = [];
    let tempArr: number[] = [];
    if (root !== null) helperQueue.push(root);
    let curNode: TreeNode;
    while (helperQueue.length > 0) {
        for (let i = 0, length = helperQueue.length; i < length; i++) {
            curNode = helperQueue.shift()!;
            tempArr.push(curNode.val);
            if (curNode.left !== null) {
                helperQueue.push(curNode.left);
            }
            if (curNode.right !== null) {
                helperQueue.push(curNode.right);
            }
        }
        res.push(tempArr);
        tempArr = [];
    }
    return res;
};
```