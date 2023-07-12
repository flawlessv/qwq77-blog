---
title: CSS中where和is的用法及其区别
tags:
  - CSS
# categories:
#   - 前端
---


深入了解 CSS 中的 :where() 和 :is() 函数
===============================

`:where()` 函数接受一个选择器列表作为参数，允许你编写更少的代码并同时设置它们的样式。在本文中，我们将讨论 `:where()` 伪类函数，并演示如何在生产环境中使用它。我们将回顾与 `:where()` 函数相关的叠加、优先级和安全性。我们还将研究一些特定的用例，并讨论它与 `:is()` 函数的异同。

1.什么是 **:where() 函数？**
----------------------

根据 [MDN](https://link.juejin.cn/?target=https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FWeb%2FCSS%2F%3Awhere "https://developer.mozilla.org/en-US/docs/Web/CSS/:where")，`:where()` 是一个 CSS 伪类函数选择器，它接受一个选择器列表作为参数，并将给定的样式应用于该列表中的任何元素，因此`:where()` 对于缩短一个较长的选择器列表非常有用。

在 CSS 中，当多个元素同时应用相同的样式规则时，我们通常会编写一长串以逗号分隔的选择器。

下面是一个例子，我们将相同的样式应用到 `header`、`main` 元素和 `footer` 元素中的所有 `<a>` 标签:

```
header a:hover,
main a:hover,
footer a:hover {
  color: green;
  text-decoration: underline;
}

```

在上面的代码片段中，我们只选择了三个元素，但是如果有大量的元素和选择器，代码将开始看起来不整洁，并且可能变得难以阅读和理解。这就是 `:where()` 伪类函数发挥作用的地方。

下面是上面的例子使用 `:where()` 函数的样子：

```
:where(header, main, footer) a:hover {
  color: red;
  text-decoration: underline;
}

```

当浏览器到达该代码片段时，该代码指示浏览器查找 `header`、`main` 和 `footer` 选择器，并定位这些选择器中的所有 `a` 标签。然后，当用户将鼠标悬停在任何这些 `a` 标签上时，浏览器应该应用指定的样式，在本例中为红色和下划线。这个伪类函数使我们能够以更短、更容易理解的方式编写一个很长的选择器列表。

2\. 组合、分割和叠加 :where() 函数
------------------------

使用 `:where()` 函数，我们可以以多种方式和组合对元素进行分组。我们可以将 `:where()` 函数放在选择器的开头、中间或结尾。下面是一个有多个选择器和样式的例子：

```
/* first list */
header a:hover,
main a:hover,
footer a:hover {
  color: green;
  text-decoration: underline;
}

/* second list */
article header > p,
article footer > p{
	color: gray;
}

/* third list */
.dark-theme button,
.dark-theme a,
.dim-theme button,
.dim-theme a{
	color: purple;
}

```

下面是相同的代码，用 `:where()` 函数重写：

```
/* first list */
/* at the beginning */
:where(header, main, footer) a:hover {
  color: red;
  text-decoration: underline;
}

/* second list */
/* in the middle */
article :where(header, footer) > p {
	color: gray;
}

/* third list */
/* at the end */
.dark-theme :where(button, a) {
	color: purple;
}
.dim-theme :where(button, a) {
	color: purple;
}

```

在第一个列表中，我们指定**红色**和**下划线**样式应应用于悬停时的 `header`、`main` 元素和 `footer` 元素。在第二个列表中，我们指定 `article`、`header` 和 `footer` 元素应该使用**灰色**样式。

为了更清晰，我们将第三个列表分为两个 `:where()` 函数。在这个列表中，我们指定 `.dark-theme`、.`dim-theme` 里的 `button` 和 `a` 元素的样式应该是**紫色**。

现在，我们将进一步减少第三个列表函数，将它们变成一个 `:where()` 函数：

```
/* stacked */
:where(.dark-theme, .dim-theme) :where(button, a) {
  color: purple;
}

```

这种减少复杂选择器列表的策略称为叠加。

3\. :where() 选择器的优先级
--------------------

`:where()` 函数选择器的优先级总是零。因此，以该函数为目标的任何元素也会自动获得 0 的优先级。这使我们能够轻松地取消任何元素的样式。

下面是一个 HTML 有序列表的例子：

```
<div>
  <h2>First list no class</h2>
  <ol>
    <li>List Item 1</li>
    <li>List Item 2</li>
  </ol>
</div>
<div>
  <h2>Second list with class</h2>
  <ol class="second-list">
    <li>List Item 1</li>
    <li>List Item 2</li>
  </ol>
</div>

<div>
  <h2>Third list with class</h2>
  <ol class="third-list">
    <li>List Item 1</li>
    <li>List Item 2</li>
  </ol>
</div>

```

在上面的代码片段中，有三个有序列表，每个列表中有两个项。第二个和第三个列表有一个给定的类，而第一个列表没有。

没有任何样式，我们可以看到每个列表是按数字顺序排列的：

![image.png](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/ff37486762ee43f781db4eb0e1781141~tplv-k3u1fbpfcp-zoom-in-crop-mark:3024:0:0:0.image)

现在，让我们添加一些样式：

```
:where(ol[class]) {
	list-style-type: none;
}

```

在上面的代码片段中，我们使用 `:where()` 伪类函数来选择应用了类的所有 `ol` 标签。

下面，我们看到第二个和第三个列表，它们都有一个类，被 `:where()` 函数作为目标，并删除了它们的 `list-style-type`：

![image.png](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/570d691f553d46a8af202863772543ce~tplv-k3u1fbpfcp-zoom-in-crop-mark:3024:0:0:0.image)

现在，让我们添加一些额外的样式：

```
:where(ol[class]) {
  list-style-type: none;
}

.second-list {
  list-style-type: disc;
}

```

只针对使用类名的第二个列表，我们可以看到它现在显示为项目符号，而第三个列表仍然没有列表样式类型：

![image.png](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/8e878fb4329c4835a0f6989c05fe5604~tplv-k3u1fbpfcp-zoom-in-crop-mark:3024:0:0:0.image)

你可能会想，“这不应该是这样吗，因为新的样式写在 `:where()` 函数样式下面？”不，它不是，我们一会儿就会看到。

让我们看看当我们把刚刚添加的代码移到代码块的顶部，并把 `:where()` 函数部分移到底部时，会发生什么：

```
.second-list {
  list-style-type: disc;
}

:where(ol[class]) {
  list-style-type: none;
}

```

注意样式仍然没有改变：

![image.png](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/f1013b793de74946b5d4743e251116aa~tplv-k3u1fbpfcp-zoom-in-crop-mark:3024:0:0:0.image)

记住，`:where()` 函数的优先级为零。

4\. :where() 选择器的安全性
--------------------

对于选择器列表，如果浏览器不能识别列表中的一个选择器，则整个选择器列表将被视为无效，并且它们的样式将不会被应用。然而，对于 `:where()` 伪类函数就不是这样了。

如果 `:where()` 函数中的元素是无效选择器的目标，则该元素将不会获得任何样式。其余的元素仍然会被设置样式。`:where()` 函数将跳过无效的选择器到下一个（有效）选择器。这就是为什么 `:where()` 被称为安全的选择器。

在下面的例子中，`:unsupported` 对于许多浏览器来说是无效的选择器。下面的代码将被正确解析，并且仍然会匹配 `:valid` 选择器，即使在不支持 `:unsupported` 选择器的浏览器中，如下所示：

```
:where(:valid, :unsupported) {
  ...
}

```

然而，在不支持 `:unsupported` 选择器的浏览器中，以下代码将被忽略，即使它们支持 `:valid` 选择器：

```
:valid, :unsupported {
  ...
}

```

5\. :where() 函数的特殊用例
--------------------

在一些特殊的用例中，`:where()` 函数可能是一个有用的工具，但也有一些情况下应该避免使用它。使用 `:where()` 伪类函数时出现的几乎所有问题都归结为优先级。因为 `:where()` 的优先级为零，我们需要非常小心地选择何时何地使用这个函数。

首先，让我们看看几个用例，在这些用例中 `:where()` 可能特别有用。

### 5.1 改进 CSS 重置

CSS 重置是指在任何其他样式之前加载一组样式规则，以清除浏览器的内置样式。CSS 重置通常放置在 CSS 样式表的顶部或开始，所以它们首先加载。开发人员通常使用它们来删除浏览器最初给几个元素的默认样式，然后才开始实际设计他们的元素和网站。CSS 重置还可以帮助消除不同浏览器之间的不一致。

CSS 重置是临时的样式，稍后会在样式化过程中更改。然而，根据 CSS 重置中使用的元素或元素组的选择器的简单性或复杂性，稍后在代码中可能很难覆盖初始样式。

例如，假设我们将网站上的所有的 `a` 标签设置为**绿色**。然后，我们稍后决定将所有 `header` 里的 `a` 标签的样式设置为**灰色**。

由于在 CSS 重置中选择的复杂性，新的（灰色）样式不会被应用。重置中的选择器比后面代码中仅针对 `header` 里的 `a` 标签使用的选择器具有更高阶的优先级，因此没有应用灰色样式。

现在，如果我们将 `:where()` 伪类函数添加到 CSS 重置中，这将自动为重置中的所有元素赋予零的优先级。这使得我们以后更容易更改样式，而不必担心优先级冲突。

### 5.2 删除样式

如果想要删除或取消样式或降低一个或一组元素的优先级，则 `:where()` 函数非常有用。

### 5.3 保持样式

如果要确保一个元素或元素集的样式或优先级在未来的任何时候都不会改变，那么不要使用 `:where()` 伪类。

6\. 什么是 :is() 函数？
-----------------

`:is()` 函数的运行方式几乎与 `:where()` 函数相同。你可以用它来简化复杂的选择器，也可以把它放在选择器的开头、中间或结尾，就像 `:where()` 函数一样。

它也是安全的，就像 `:where()` 函数一样。因此，当其中一个选择器无效时，浏览器将忽略该选择器，但有效选择器的样式将添加到所选元素中。

7\. :where() 和 :is() 函数的区别
--------------------------

这两个函数的区别在于 `:where()` 函数的优先级总是零，则 `:is()` 函数的优先级取决于其最特定参数的优先级。例如，让我们看看 `header` 元素中的段落文本：

```
<header>
  <p>This is a paragraph text.</p>
</header>

```

然后，让我们尝试使用四种不同的选择器来改变文本颜色：

```
header p {
  color: blue;
}

:is(header, section) p {
  color: green;
}

p {
  color: blue;
}

:where(header, section) p {
  color: blue;
}

```

第一个选择器将文本的颜色设置为蓝色。使用 `:is()` 的第二个选择器与第一个选择器具有相同的优先级，但由于它位于第一个选择器之后，因此它将文本颜色从蓝色更改为绿色。第三个选择器的优先级低于第一个和第二个选择器，对文本没有影响。最后是第四个，它使用 `:where()` 函数对文本没有影响，因为它的零优先级。

8\. 浏览器兼容性
----------

所有浏览器，无论是桌面浏览器还是移动浏览器，都完全支持 CSS `:where()` 函数，包括对其安全特性的支持。因此，你 不必担心你 的样式是否会在浏览器中正确呈现。
