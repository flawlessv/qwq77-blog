---
title: 使用TypeScript实现循环链表
cover: "https://www.dmoe.cc/random.php"
tags:
  - TypeScript
  - 链表
categories:
  - 数据结构
---

#### 只需要重写以下方法即可

```ts
class CircularLinkedList<T> extends LinkedList<T> {
  append(value: T): void {
    super.append(value);
    //拿到最后一个节点next指向第一个节点
    this.tail!.next = this.head;
  }
  insert(value: T, position: number): boolean {
    const isSuccess = super.insert(value, position);
    if (isSuccess && (position === this.length - 1 || position === 0)) {
      this.tail!.next = this.head;
    }
    return isSuccess;
  }
  removeAt(position: number): T | null {
    const value = super.removeAt(position);
    if (value && this.tail && (position === 0 || position === this.length)) {
      this.tail.next = this.head;
    }
    return value;
  }
}
```
