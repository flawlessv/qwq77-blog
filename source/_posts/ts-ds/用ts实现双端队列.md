---
title: 使用TypeScript实现双端队列
cover: "https://www.dmoe.cc/random.php"
tags:
  - TypeScript
  - 队列
categories:
  - 数据结构
---

### IQueun接口

```ts
interface IQueun<T> extends ISQ{
 enqueun(values:T):number
 dequeun():T|undefined
}
```

### 普通队列代码实现

```ts
export default class ArrayQueun<T> implements IQueun<T>{
    protected data:T[]=[]
    //入队方法
    enqueun(values: T): number {
        this.data.push(values)
        return this.size()
    }
    //出队方法
    dequeun(): T|undefined {
        return this.data.shift()
    }
    //返回队列的长度
    size(): number {
        return this.data.length
    }
    //判断队列是否为空
    isEmpty(): boolean {
        return this.data.length===0
    }
}
```

### 双端队列代码实现

```ts
class ArrayDeque<T> extends ArrayQueun<T> {
  addFront(value: T) {
    this.data.unshift(value);
  }
  removeBack(): T | undefined {
    return this.data.pop();
  }
}
```

