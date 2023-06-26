---
title: 使用TypeScript实现二叉树
tags:
  - TypeScript
  - 数据结构
---

### TreeNode 接口

```ts
export class TreeNode<T> extends Node<T> {
  left: TreeNode<T> | null = null;
  right: TreeNode<T> | null = null;
  parent: TreeNode<T> | null = null;
  get isLeft(): boolean {
    return !!(this.parent && this.parent?.left === this);
  }
  get isRight(): boolean {
    return !!(this.parent && this.parent?.right === this);
  }
}
```

### 代码实现

#### BSTree

```ts
export class BSTree<T> {
  private root: TreeNode<T> | null = null;
  print() {
    btPrint(this.root);
  }

  //获取最值操作：最大值和最小值
  getMaxValue(): T | null {
    let current = this.root;
    while (current && current.right) {
      current = current.right;
    }
    return current?.value ?? null;
  }
  getMinValue(): T | null {
    let current = this.root;
    while (current && current.left) {
      current = current.left;
    }
    return current?.value ?? null;
  }
  //搜素指定的节点
  private searchNode(value: T): TreeNode<T> | null {
    let current = this.root;
    let parent: TreeNode<T> | null = null;
    while (current) {
      if (current.value === value) {
        return current;
      }
      //保存父节点
      parent = current;
      if (current.value > value) {
        //如果当前值大于要查找的值，去左边查找
        current = current.left;
      } else {
        current = current.right;
      }
      if (current) current.parent = parent;
    }
    return null;
  }
  //搜索
  search(value: T): boolean {
    return this.searchNode(value)?.value === value;
  }

  private getSuccessor(delNode: TreeNode<T>): TreeNode<T> {
    //获取右子树
    let current = delNode.right;
    let successor: TreeNode<T> | null = null;
    while (current) {
      successor = current;
      current = current.left;
      if (current) {
        current.parent = successor;
      }
    }
    //拿到了后继节点
    if (successor !== delNode.right) {
      successor!.parent!.left = successor!.left;
      successor!.right = delNode.right;
    }
    //将删除节点的left赋值给后继节点的left
    successor!.left = delNode.left;
    return successor!;
  }

    // 4:有两个子节点
    else {
      const successor = this.getSuccessor(current);
      if (current === this.root) {
        this.root = successor;
      } else if (current.isLeft) {
        current.parent!.left = successor;
      } else {
        current.parent!.right = successor;
      }
    }
    return true;
  }
```

#### 插入数据的操作

```ts
  insert(value: T) {
    // 1:根据传入的value创建新的TreeNode节点
    const newNode = new TreeNode<T>(value);
    // 2:判断当前是否已经有根节点
    if (!this.root) {
      //当前树为空
      this.root = newNode;
    } else {
      //树中已经有了其他值
      this.insertNode(this.root, newNode);
    }
  }
  private insertNode(node: TreeNode<T>, newNode: TreeNode<T>) {
    if (newNode.value < node.value) {
      //去左边继续查找空白位置
      if (node.left === null) {
        //node的左子树为空
        node.left = newNode;
      } else {
        //左子树不为空，递归继续查找空白位置
        this.insertNode(node.left, newNode);
      }
    } else {
      //去右边继续查找空白位置
      if (node.right === null) {
        //node的左子树为空
        node.right = newNode;
      } else {
        //右子树不为空，递归继续查找空白位置
        this.insertNode(node.right, newNode);
      }
    }
  }
```

#### 遍历的操作

```ts
 //先序遍历
  preOrderTraverse() {
    this.preOrderTraverseNode(this.root);
  }
  private preOrderTraverseNode(node: TreeNode<T> | null) {
    if (node) {
      console.log(node.value);
      this.preOrderTraverseNode(node.left);
      this.preOrderTraverseNode(node.right);
    }
  }
  // 中序遍历
  inOrderTraverse() {
    this.inOrderTraverseNode(this.root);
  }
  private inOrderTraverseNode(node: TreeNode<T> | null) {
    if (node) {
      this.inOrderTraverseNode(node.left);
      console.log(node.value);
      this.inOrderTraverseNode(node.right);
    }
  }
  // 后序遍历
  postOrderTraverse() {
    this.postOrderTraverseNode(this.root);
  }
  private postOrderTraverseNode(node: TreeNode<T> | null) {
    if (node) {
      this.postOrderTraverseNode(node.left);
      this.postOrderTraverseNode(node.right);
      console.log(node.value);
    }
  }
  // 层序遍历
  levelOrderTraverseNode() {
    // 1:如果没有跟节点，不需要遍历
    if (!this.root) return;
    const queue: TreeNode<T>[] = [];
    //第一个节点是根节点
    queue.push(this.root);
    //遍历队列中的所有节点
    while (queue.length) {
      const current = queue.shift()!;
      console.log(current.value);
      if (current.left) {
        queue.push(current.left);
      }
      if (current.right) {
        queue.push(current.right);
      }
    }
  }
```

#### 实现删除操作

```ts
  remove(value: T): boolean {
    // 1:删除：判断当前是否有这个value
    const current = this.searchNode(value);
    if (!current) return false;
    // 2:获取三个东西：当前节点/父节点/是左子节点还是右子节点
    // console.log("当前节点", current.value, "父节点", current.parent?.value);
    // 2.1如果删除的是叶子节点
    if (current.left === null && current.right === null) {
      if (current === this.root) {
        this.root = null;
      } else if (current.isLeft) {
        current.parent!.left = null;
      } else {
        current.parent!.right = null;
      }
    }

    // 3:只有一个子节点：左子节点
    else if (current.right === null) {
      if (current === this.root) {
        this.root = current.left;
      } else if (current.isLeft) {
        current.parent!.left = current.left;
      } else {
        current.parent!.right = current.left;
      }
    } else if (current.left === null) {
      if (current === this.root) {
        this.root = current.right;
      } else if (current.isLeft) {
        current.parent!.left = current.right;
      } else {
        current.parent!.right = current.right;
      }
}
    }
```
