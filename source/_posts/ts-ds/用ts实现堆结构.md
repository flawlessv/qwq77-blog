---
title: 用ts实现堆结构
cover: "https://www.dmoe.cc/random.php"
tags:
  - TypeScript
  - 堆
categories:
  - 数据结构
---

#### 代码实现

```ts
class Heap<T> {
  private heap: T[];

  constructor(private compareFn: (a: T, b: T) => number) {
    this.heap = [];
  }

  public size(): number {
    return this.heap.length;
  }

  public isEmpty(): boolean {
    return this.size() === 0;
  }

  // 获取父节点下标
  private getParentIndex(index: number): number {
    return Math.floor((index - 1) / 2);
  }

  // 获取左子节点下标
  private getLeftChildIndex(index: number): number {
    return 2 * index + 1;
  }

  // 获取右子节点下标
  private getRightChildIndex(index: number): number {
    return 2 * index + 2;
  }

  // 上移节点
  private siftUp(index: number): void {
    if (index > 0) {
      const parentIndex = this.getParentIndex(index);
      if (this.compareFn(this.heap[parentIndex], this.heap[index]) < 0) {
        [this.heap[parentIndex], this.heap[index]] = [
          this.heap[index],
          this.heap[parentIndex],
        ];
        this.siftUp(parentIndex);
      }
    }
  }

  // 下移节点
  private siftDown(index: number): void {
    const leftIndex = this.getLeftChildIndex(index);
    const rightIndex = this.getRightChildIndex(index);
    let maxIndex = index;
    if (
      leftIndex < this.size() &&
      this.compareFn(this.heap[leftIndex], this.heap[maxIndex]) > 0
    ) {
      maxIndex = leftIndex;
    }
    if (
      rightIndex < this.size() &&
      this.compareFn(this.heap[rightIndex], this.heap[maxIndex]) > 0
    ) {
      maxIndex = rightIndex;
    }
    if (maxIndex !== index) {
      [this.heap[index], this.heap[maxIndex]] = [
        this.heap[maxIndex],
        this.heap[index],
      ];
      this.siftDown(maxIndex);
    }
  }

  // 插入节点
  public insert(value: T): void {
    this.heap.push(value);
    this.siftUp(this.size() - 1);
  }

  // 获取最大值/最小值（不删除）
  public peek(): T | null {
    return this.isEmpty() ? null : this.heap[0];
  }

  // 删除最大值/最小值
  public extract(): T | null {
    if (this.isEmpty()) {
      return null;
    }
    const removedValue = this.heap[0];
    const lastValue = this.heap.pop();
    if (this.size() > 0 && lastValue !== undefined) {
      this.heap[0] = lastValue;
      this.siftDown(0);
    }
    return removedValue;
  }
}
```

#### 使用示例

```ts
// 定义一个最大堆
const maxHeap = new Heap<number>((a, b) => b - a);

// 插入节点
maxHeap.insert(4);
maxHeap.insert(7);
maxHeap.insert(10);
maxHeap.insert(1);
maxHeap.insert(8);

// 获取最大值
console.log(maxHeap.peek()); // 输出：10

// 删除最大值，并输出剩余堆
while (!maxHeap.isEmpty()) {
  console.log(maxHeap.extract()); // 输出：10 8 7 4 1
}
```
