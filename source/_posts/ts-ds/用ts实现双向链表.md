---
title: 使用TypeScript实现双向链表
tags:
  - TypeScript
  - 链表
categories:
  - 数据结构
---

### DoublyNode 接口

```ts
export class Node<T> {
  value: T;
  next: Node<T> | null = null;
  constructor(value: T) {
    this.value = value;
  }
}
export class DoublyNode<T> extends Node<T> {
  prev: DoublyNode<T> | null = null;
  next: DoublyNode<T> | null = null;
}
```
### 代码实现

#### 需要重写的属性

```ts
 protected head: DoublyNode<T> | null = null;
  protected tail: DoublyNode<T> | null = null;
```

#### 向链表尾部中添加元素

```ts
 append(value: T): void {
    const newNode = new DoublyNode(value);
    if (!this.head) {
      this.head = newNode;
      this.tail = newNode;
    } else {
      this.tail!.next = newNode;
      newNode.prev = this.tail;
      this.tail = newNode;
    }
    this.length++;
  }
```

####  向头部插入节点

```ts
  prepend(value: T): void {
    const newNode = new DoublyNode(value);
    if (!this.head) {
      this.head = newNode;
      this.tail = newNode;
    } else {
      newNode.next = this.head;
      this.head.prev = newNode;
      this.head = newNode;
    }
    this.length++;
  }
```
#### 向指定位置插入节点
```ts
   insert(value: T, position: number): boolean {
    if (position < 0 || position > this.length) return false;
    if (position === 0) {
      this.prepend(value);
    } else if (position === this.length) {
      this.append(value);
    } else {
      const newNode = new DoublyNode(value);
      const current = this.getNode(position) as DoublyNode<T>;
      current.prev!.next = newNode;
      newNode.next = current;
      newNode.prev = current.prev;
      current.prev = newNode;
      this.length++;
    }
    return true;
  }
```
#### 删除指定位置节点
```ts
removeAt(position: number): T | null {
    if (position < 0 || position >= this.length) return null;
    let current = this.head;
    if (position === 0) {
      if (this.length === 1) {
        this.head = null;
        this.tail = null;
      } else {
        this.head = this.head!.next;
        this.head!.prev = null;
      }
    } else if (position === this.length - 1) {
      current = this.tail;
      this.tail = this.tail!.prev;
      this.tail!.next = null;
    } else {
      current = this.getNode(position) as DoublyNode<T>;
      current.next!.prev = current.prev;
      current.prev!.next = current.next;
    }
    this.length--;
    return current?.value ?? null;
  }
```
