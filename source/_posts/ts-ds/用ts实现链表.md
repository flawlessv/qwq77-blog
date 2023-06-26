---
title: 使用TypeScript实现链表
tags:
  - TypeScript
  - 数据结构
---

### ILinkedList 接口

```ts
import ISQ from "../types/ISQ";

interface ILinkedList<T> extends ISQ {
  append(value: T): void;
  traverse(): void;
  insert(value: T, position: number): boolean;
  removeAt(position: number): T | null;
  get(position: number): T | null;
  update(value: T, position: number): boolean;
  indexof(value: T): number;
  remove(value: T): T | null;
}
export default ILinkedList;
```
### 封装Node类
```ts
class Node<T> {
  value: T;
  next: Node<T> | null = null;
  constructor(value: T) {
    this.value = value;
  }
}
```
### 代码实现

#### 需要封装的属性

```ts
export default class LinkedList<T> implements ILinkedList<T> {
  protected head: Node<T> | null = null;
  protected length: number = 0;
  //新增属性
  protected tail: Node<T> | null = null;
  size() {
    return this.length;
  }



class Node<T> {
  value: T;
  next: Node<T> | null = null;
  constructor(value: T) {
    this.value = value;
  }
}

export {};
```

#### 需要封装的私有方法

```ts
//获取指定位置的节点
  private getNode(position: number): Node<T> | null {
    let index = 0;
    let current = this.head;
    while (index++ < position && current) {
      current = current?.next;
    }
    return current;
  }
  //判断该节点是否是tail
  private isTail(node: Node<T> | null): boolean {
    return this.tail === node;
  }
```

#### 向链表中添加元素

```ts
  append(value: T) {
    const newNode = new Node<T>(value);

    if (!this.head) {
      this.head = newNode;
    } else {
      this.tail!.next = newNode;
    }
    this.tail = newNode;

    this.length++;
  }
```

#### traverse 遍历链表方法

```ts
traverse() {
  let current = this.head;
  const values: T[] = [];
  while (current) {
    values.push(current.value);
    if (this.isTail(current)) {
      //如果是最后一个节点
      current = null;
    } else {
      current = current.next;
    }
  }
  //循环链表
  if (this.head && this.tail?.next === this.head) {
    values.push(this.head.value);
  }
  console.log(values.join("->"));
}
```
#### 向指定位置插入节点
```ts
  insert(value: T, position: number): boolean {
    //判断插入下标是否越界
    if (position < 0 || position > this.length) {
      return false;
    }
    const newNode = new Node(value);
    if (position === 0) {
      newNode.next = this.head;
      this.head = newNode;
    } else {
      const previous = this.getNode(position - 1);
      previous!.next = newNode;
      newNode.next = previous?.next.next ?? null;
      if (position === this.length) {
        this.tail = newNode;
      }
    }
    this.length++;
    return true;
  }
```
#### 删除指定位置节点
```ts
removeAt(position: number): T | null {
    if (position < 0 || position >= this.length) {
      return null;
    }
    let current = this.head;
    let previous: Node<T> | null = null;
    if (position === 0) {
      this.head = this.head?.next ?? null;
      if (this.length === 1) {
        this.tail = null;
      }
    } else {
      previous = this.getNode(position - 1);
      current = previous?.next ?? null;
      previous!.next = previous?.next?.next ?? null;
      if (position === this.length - 1) {
        this.tail = previous;
      }
    }
    this.length--;
    return current?.value ?? null;
  }
```
#### 获取指定位置元素
```ts
 get(position: number): T | null {
    if (position < 0 || position >= this.length) {
      return null;
    }
    return this.getNode(position)?.value ?? null;
  }
```
#### 更新指定位置的value
```ts
  update(value: T, position: number): boolean {
    if (position < 0 || position > this.length) {
      return false;
    }
    let current = this.getNode(position);
    current!.value = value;
    return true;
  }
```
#### 获取链表指定值的索引
```ts
 indexof(value: T): number {
    let current = this.head;
    let index = 0;
    while (current) {
      if (current.value === value) {
        return index;
      }
      if (!this.isTail(current)) {
        current = current.next;
      } else {
        current = null;
      }
      index++;
    }
    return -1;
  }
```
#### 根据值删除指定位置元素
```ts
 remove(value: T): T | null {
    const index = this.indexof(value);
    return this.removeAt(index);
  }

  isEmpty(): boolean {
    return this.length === 0;
  }
```