---
title: CSScolumns分栏布局教程
tags:
  - 实习收获
  - CSS
categories:
  - 实习
---

### 一、前言&索引

Multiple-column布局，也称多列布局、多栏布局，我自己喜欢叫做分栏布局，这种布局可以讲内容布局到一组列框，类似于报纸上的排版。

![报纸分栏排版](https://image.zhangxinxu.com/image/blog/201901/columns-s.jpg)

分栏布局非常特殊，有别于传统布局方法，它将包括包括所有子元素在内的所有内容拆分为列，这与我们打印网页时候时页面内容分割成不同的页面的方式类似。

分栏布局IE10+都可以使用，API稳定，移动端兼容性比flex布局要好，虽然设计初衷不一样，但很多布局都可以实现。甚至某些场景下，只能使用分栏布局才能实现。很有学习的必要。

与分栏布局相关的CSS属性包括：

| 直接相关属性 | 间接相关属性 |
| --- | --- |
| 
*   [column-width](about:blank#column-width)
*   [column-count](about:blank#column-count)
*   [columns](about:blank#columns)
*   [column-rule-color](about:blank#column-rule-color)
*   [column-rule-style](about:blank#column-rule-style)
*   [column-rule-width](about:blank#column-rule-width)
*   [column-rule](about:blank#column-rule)
*   [column-span](about:blank#column-span)
*   [column-fill](about:blank#column-fill)
*   [column-gap](about:blank#column-gap)

 | 

*   [break-after](about:blank#break-after)
*   [break-before](about:blank#break-before)
*   [break-inside](about:blank#break-inside)

 |

### 二、直接相关CSS属性

#### 1\. column-width

`column-width`表示每一栏/列的最佳宽度。

如果我们只设定`column-width`，浏览器会自动根据现有容器宽度划分栏目的个数。

**语法如下：**

```
column-width: <length> | auto;
```

其中：

**<length>**

表示设定的最佳列宽值。实际呈现的每一栏的宽度可能与指定值不同，具体内容参见下面的细节描述。

**auto**

默认值。表示每一栏的宽度由其它CSS属性决定，例如`[column-count](about:blank#column-count)`。

**一些细节：**

1.  `column-width`有时候会无效。例如容器宽度400像素，设定的每一栏宽度是300像素，不足以分栏，此时内容填充填充表现为充分利用可用空间，最终呈现的列宽比设定的更宽。又例如容器宽度400像素，`column-width`设置为500像素，则最终分栏宽度不会超过容器宽度，比设定的500像素要小。
2.  `column-width`不支持负值，也不支持百分比值。

**实地演示：**

点击下面的选项卡，感受下不同`column-width`属性值下的布局表现：

column-width:autocolumn-width:8%（无效）column-width:80pxcolumn-width:8em

CSS `column-width`属性指定多列布局中的理想列宽。容器将具有尽可能多的列，其中任何一列的宽度都不小于列宽值。如果容器的宽度小于指定值，则单列的宽度将小于声明的列宽。

此属性可以帮助您创建适合不同屏幕大小的响应式设计。尤其是在`column-count`属性（具有优先权）存在的情况下，必须指定所有相关的长度值以获得精确的列宽度。在水平文本中，这些长度值包括`width`、`column-width`、`column-gap`，以及`column-rule-width`。

#### 2\. column-count

`column-count`表示理想的分栏数目。

**语法如下：**

```
column-count: <integer> | auto;
```

其中：

**<integer>**

表示分栏数目，整数值。

**auto**

默认值。表示分栏数目由其它CSS属性决定，例如`[column-width](about:blank#column-width)`。

**一些细节：**

1.  `column-count`与`column-width`都有可能有更高的优先级，要看具体场景。优先级计算诀窍就是统一转换`column-count`值，哪个小就使用哪一个。
2.  `column-count`不支持负值，也不支持`0`。

**实地演示：**

点击下面的选项卡，感受下不同`column-count`属性值下的布局表现：

column-count:autocolumn-count:2column-count:2;  
column-width:200pxcolumn-count:4;  
column-width:200px

这个选项卡测试切换效果建议在PC端浏览器上体验，在移动端，由于宽度限制感受不到后两个选项的差异。

在PC桌面端，容器宽度大约700像素出头一点，此时`column-width:200px`换算成`column-count`大约3.6的样子。于是，选项卡3分成了2栏，因为`column-count:2`值更小；而选项卡4由于`column-width`换算值更小，因此`column-width`优先级更高，最终分成了3栏显示。

其中，我们重点关注选项卡3和选项卡4。在PC算，由于容器宽度大约700像素出头一点，因此`column-width:200px`可以近似看成`column-count`为3.6的样子。还记不记得上面提到的优先级计算诀窍：哪个值小哪个优先级高。于是，选项卡3分成了2栏，因为`column-count:2`值更小；而选项卡4由于`column-width`换算值更小，因此`column-width`优先级更高，最终分成了3栏显示。

另外，从两栏效果可以看出，columns每一个栏目的高度并不总是相等的，内容的分割也不总是均匀的，浏览器有一套自己的算法。

#### 3\. columns

`columns`是`column-width`和`column-count`属性的缩写。举几个使用的例子：

```
/\* 栏目宽度 \*/
columns: 18em;

/\* 栏目数目 \*/
columns: auto;
columns: 2;

/\* 同时定义宽度和数目 \*/
columns: 2 auto;
columns: auto 12em;
columns: auto auto;
```

不展开。

#### 4\. column-rule-color

`column-rule-color`表示每个栏目中间分隔线的颜色。

**语法如下：**

```
column-rule-color: <color>
```

支持的属性值和`border-color`是一模一样的，例如：

```
column-rule-color: red;
column-rule-color: rgb(255, 0, 0);
column-rule-color: transparent;
column-rule-color: hsla(0, 100%, 50%, 0.5);
```

默认值是当前`color`属性的计算值。

**实例如下：**

```
column-rule-style: dotted;
column-rule-color: red;
```

实时效果如下：

由于`column-rule`默认的分隔线的类型是`none`，因此，我们必须要指定`column-rule-style`，否则会看不到分隔线。`column-rule-*`相关属性值和`border-*`是一样的。

#### 5\. column-rule-style

`column-rule-style`表示每个栏目中间分隔线的类型。支持的属性值和`border-style`是一模一样的，例如：

```
column-rule-style: none;
column-rule-style: hidden;
column-rule-style: dotted;
column-rule-style: dashed;
column-rule-style: solid;
column-rule-style: double;
column-rule-style: groove;
column-rule-style: ridge;
column-rule-style: inset;
column-rule-style: outset;
```

每个属性值具体效果可以点击下面选项卡进行体验：

nonehiddendotteddashedsoliddoublegrooveridgeinsetoutset

其中`dotted`表示虚点，`dashed`表示虚线，`solid`表示实线。这三个比较常用，就不多展开。然后着重提下后面几个，首先是`double`，`double`表示  
双线边框，顾名思意，两根线，且为实线。虽然平常我们使用少，但是兼容性非常好。视觉表现为线框-透明-线框。其它`column-rule-style`类型，如`inset`（内凹），`outset`（外凸），`groove`（沟槽），`ridge`（山脊），风格老土过时，且兼容性惨不忍睹，因此，没有任何实用价值，大家无需关心。

科学研究表明，对于大多数人而言，无论在这里写的是什么文字，都不会被读者注意到。

#### 5\. column-rule-width

`column-rule-width`表示每个栏目中间分隔线的宽度大小。支持的属性值和`border-width`是一模一样的，例如：

```
/\* 关键字值 \*/
column-rule-width: thin;
column-rule-width: medium;  /\* 默认值 \*/
column-rule-width: thick;

/\* 具体长度值 \*/
column-rule-width: 1px;
column-rule-width: 2.5em;
```

我们平常使用`column-rule-width`几乎全是固定的数值，比方说`column-rule-width:1px`之类，于是对关键字属性值不太了解，这里介绍下。`column-rule-width`支持三个关键字属性值，分别是`thin`，`medium`（默认值）和`thick`，对应的具体尺寸大小如下：

1.  **`thin`**：薄薄的，等同于`1px`；
2.  **`medium`**（默认值）：薄厚均匀，等同于`3px`；
3.  **`thick`**：厚厚的，等同于`5px`；

不知大家有没有想过这么一个问题：为什么默认宽度大小是`medium`，也就是3px，明明thin（1px）宽度更常用吧？这是因为……`column-rule-style:double`至少3px才有效果！

#### 6\. column-rule

`column-rule`是`[column-rule-width](about:blank#column-rule-width)`，`[column-rule-style](about:blank#column-rule-style)`和`[column-rule-color](about:blank#column-rule-color)`这3个CSS属性的缩写。正如`border`是`border-style`，`border-width`和`border-color`的缩写一样。

其他没什么好说的，几个属性值顺序不讲究，随便。除了`[column-rule-style](about:blank#column-rule-style)`之外那其它两个属性可以缺省。

#### 7\. column-span

`column-span`有点类似于表格布局中的`colspan`这个HTML属性，表示某一个内容是否跨多栏显示。

**语法**

```
column-span: none;
column-span: all;
```

其中：

**none**

表示不横跨多栏，默认值。

**all**

表示横跨所有垂直列。

我们一起来看一个例子，就知道这个属性是干嘛用的了：

column-span:nonecolumn-span:all

在HTML中，类似单元格`<td>`元素可以设置`colspan`属性，表示合并单元格，例如`colspan="3"`表示3个普通单元格合并成1个大的单元格。

`column-span`这个CSS属性作用与之类似，只是不能指定具体的数目。要么不跨列，要跨就跨全部条列。

在我们想要在垂直分栏显示的文章中插一个横贯整个页面的广告的时候，就可以使用这个属性。或者单纯只是希望上下再垂直分栏显示，也可以使用该属性。

实际开发的时候，非指定某个元素`column-span:all`，没有文本内容，就一个高度，或者加个水平边框，就可以将文章内容进一步上下分栏。于是，一篇文章的内容，就如报纸排版一样，想要在哪里分栏就随心所欲了。

当然，插入通栏广告也可以使用该属性。

#### 8\. column-fill

`column-fill`作用是当内容分栏的时候，如何平衡每一栏填充的内容。

**语法**

```
column-fill: auto;
column-fill: balance;
column-fill: balance-all;

```

其中：

**auto**

按顺序填充每一列。内容只占用它需要的空间。

**balance**

默认值。尽可能在列之间平衡内容。在分隔断开的上下文中，只有最后一个片段是平衡的。举例来说就是有多个`<p>`元素，正好最后一个`<p>`换行了，那这个`<p>`元素的内容前后等分，保持平衡。这就会造成最后一栏内容较少的情况。

**balance-all**（可忽略）

尽可能在列之间平衡内容。在分隔断开的上下文中，所有片段都是平衡的。

我们一起来看一个与`column-fill`属性相关的demo（目前仅Firefox浏览器有正确表现）：

column-fill:autocolumn-fill:balancecolumn-fill:balance-all

这是一堆分成多个的文本列。CSS\`column-fill\`属性是用于将内容均匀地分布在一起所有列。

`column-fill`这个属性的准确渲染需要在Firefox浏览器下才可以看到。当我们点击`auto`的时候，所有的文字内容应该挤在最左边一栏中才是正确的。但是Chrome和IE下却和`balance`属性值表现一样。

上面demo当我们点击`'auto'`这个选项卡的时候，正确的表现应该如下图所示：

![正确的渲染表现](https://image.zhangxinxu.com/image/blog/201901/2019-01-30_233729.png)

若要让所有浏览器下`column-fill:auto`都有效果，需要给容器元素设置固定的高度值菜系。

还有，根据我在IE，Chrome和Firefox浏览器下测试，这几个浏览器点击`balance-all`都没能识别。我查看官方草案文档，也没有`balance-all`的示意，该属性值大家可以忽略。

#### 9\. column-gap

`column-gap`表示每一栏之间的那个空白间隙大小。

**语法**

```
column-gap: normal | <length-percentage>;
```

**具体**

```
/\* 关键字值 \*/
column-gap: normal; 

/\* 长度值 \*/
column-gap: 3px;
column-gap: 3em;

/\* 百分比值 \*/
column-gap: 3%;
```

其中：

**normal**

默认值。在多栏布局中为`1em`，在其它类型的布局中为`0`。

**<length>**

具体的长度值。不支持负数。

**<percentage>**

百分比值。和`column-width`不同，`column-gap`支持百分比值。同样，不能是负数。

**实地demo演示**

column-gap:normalcolumn-gap:8%column-gap:80pxcolumn-gap:8em

虽然`column-gap`属性的默认值`normal`最终的表现就是`1em`，但并不表示可以和数值属性值产生`transition`过渡效果。因此，当我们点击到第一个选项卡的时候，宽度变化是突然的，而不是连续的。

`column-gap`和`columns`属性发生冲突的时候，例如，`column-gap`太大，导致空间不足，此时，`column-gap`是会被舍弃的。

### 三、间接相关CSS属性

每个可能的断点（换句话说，每个元素边界）受三个属性的影响：前一个元素的`break-after`值，下一个元素的`[break-before](about:blank#break-before)`值，以及包含元素的`[break-inside](about:blank#break-inside)`值。

下面要介绍的3个属性，可以控制分栏布局中当前元素前后是否允许分栏。

#### 1\. break-after

`break-after`这个CSS属性定义页面，列或区域中断在生成的框之后应该如何表现。如果没有生成框，则忽略该属性。

`break-after`支持属性很多，但大多浏览器不支持，我们目前只要关注下面两个属性值就好了：

```
break-after: auto;
break-after: avoid;
```

其中：

**auto**

允许但不强制在主框之后插入任何中断（page，column或region布局下）。

**avoid**

避免在主体框后插入任何分隔符（page，column或region布局下）。

#### 2\. break-before

`break-before`这个CSS属性定义页面，列或区域中断在生成的框之前应该如何表现。如果没有生成框，则忽略该属性。

`break-before`支持属性很多，但大多浏览器不支持，我们目前只要关注下面两个属性值就好了：

```
break-before: auto;
break-before: avoid;
```

其中：

**auto**

允许但不强制在主框之前插入任何中断（page，column或region布局下）。

**avoid**

避免在主体框前插入任何分隔符（page，column或region布局下）。

#### 3\. break-inside

`break-inside`这个CSS属性定义页面、列或区域发生中断时候的元素该如何表现。如果没有中断，则忽略该属性。

`break-inside`支持属性相对少一些，同样的，我们目前只要关注下面两个属性值就好了：

```
break-inside: auto;
break-inside: avoid;
```

其中：

**auto**

元素可以中断。

**avoid**

元素不能中断。

**demo实例页面**

拿column分栏布局举例，分栏布局在流动和平衡内容方面做得很好。不幸的是，并非所有元素都能优雅地流动。有时元素会断开分布在两个列中。如下图所示：

![文字断行显示](https://image.zhangxinxu.com/image/blog/201901/2019-01-31_005757.png)

有时候，我们希望我们的条目一个元素一个元素都是独立的，前后都不断开，此时，就可以使用`break-inside:avoid`实现：

```
.list {
  -webkit-column-break-inside: avoid; /\* Chrome, Safari, Opera \*/
            page-break-inside: avoid; /\* Firefox \*/
                 break-inside: avoid; /\* IE 10+, Chrome, Safari, Opera \*/
}
```

此时效果如下截图：

![前后不断开的效果截图](https://image.zhangxinxu.com/image/blog/201901/2019-01-31_010224.png)

您可以狠狠地点击这里：[CSS break-inside与分栏不断开demo](https://www.zhangxinxu.com/study/201901/css-break-inside-demo.php)

**其他**

应该是上个月，还介绍了一个名为`box-decoration-break`的CSS属性，也与columns布局是相关的，其作用更多的是元素断开后的装饰表现。有兴趣可以参见这篇文章：“[CSS/CSS3 box-decoration-break属性简介](https://www.zhangxinxu.com/wordpress/2019/01/css-css3-box-decoration-break/)”。

### 四、一些特殊布局应用举例

CSS3 columns多栏布局可以实现水平翻书阅读效果。

![水平翻书阅读效果](https://image.zhangxinxu.com/image/blog/201901/read-h-columns-s.gif)

具体见这篇文章：“[基于CSS3 column多栏布局实现水平翻页交互](https://www.zhangxinxu.com/wordpress/?p=5945)”。


