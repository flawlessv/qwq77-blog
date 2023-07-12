---
title: 使用TypeScript实现栈
tags:
  - TypeScript
  - 栈
categories:
  - 数据结构
---

### IStack 接口

```ts
interface IStack<T> extends ISQ {
  push(element: T): void;
  pop(): T | undefined;
  peek(): T | undefined;
}
```

### 代码实现

```ts
class ArrayStack<T> implements IStack<T> {
  private data: T[] = [];
  push(element: T) {
    this.data.push(element);
  }
  pop(): T | undefined {
    return this.data.pop();
  }
  isEmpty(): boolean {
    return this.data.length === 0;
  }
  peek(): T | undefined {
    return this.data[this.data.length - 1];
  }
  size(): number {
    return this.data.length;
  }
}
```
