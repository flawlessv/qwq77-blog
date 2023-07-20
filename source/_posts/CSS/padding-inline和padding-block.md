---
title: padding-inline和padding-block
tags:
  - CSS
# categories:
#   - 前端
---
# padding-inline和padding-block

在CSS盒模型中，padding是指一个元素内部边框和内容之间的空间。但是，CSS中的坐标系不同于我们常见的笛卡尔坐标系。CSS中的坐标系是基于文本方向的，文本方向可以是水平的（从左到右）或垂直的（从上到下）。

在CSS3中，引入了一个新的属性`padding-inline`和`padding-block`，用于指定元素在文本方向上的内边距。`padding-inline`用于水平方向，`padding-block`用于垂直方向。

## padding-inline

`padding-inline`属性用于指定元素在水平方向上的内边距。对于从左到右的文本方向，`padding-inline`等同于`padding-left`和`padding-right`的和。而对于从右到左的文本方向，`padding-inline`等同于`padding-right`和`padding-left`的和。

示例代码：

```css
div {
  padding-inline: 20px;
}
```

示例效果图：

![padding-inline示例效果图](./padding-inline.png)

## padding-block

`padding-block`属性用于指定元素在垂直方向上的内边距。对于从上到下的文本方向，`padding-block`等同于`padding-top`和`padding-bottom`的和。而对于从下到上的文本方向，`padding-block`等同于`padding-bottom`和`padding-top`的和。

示例代码：

```css
div {
  padding-block: 20px;
}
```

示例效果图：

![padding-block示例效果图](./padding-block.png)

## 总结

`padding-inline`和`padding-block`是CSS3中引入的属性，用于指定元素在文本方向上的内边距。`padding-inline`用于水平方向，`padding-block`用于垂直方向。在从左到右的文本方向下，`padding-inline`等同于`padding-left`和`padding-right`的和。在从右到左的文本方向下，`padding-inline`等同于`padding-right`和`padding-left`的和。在从上到下的文本方向下，`padding-block`等同于`padding-top`和`padding-bottom`的和。在从下到上的文本方向下，`padding-block`等同于`padding-bottom`和`padding-top`的和。

这些属性可以很方便地调整元素在不同文本方向下的内边距，提高页面的适配性。