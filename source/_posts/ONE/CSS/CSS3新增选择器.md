---
title: CSS3新增选择琪
tags:
  - CSS
# categories:
#   - 前端
---
一、CSS3概述
--------

### 1.1 CSS3历史

> CSS3 是层叠样式表(Cascading Style Sheets) 语言的最新进展，目的在于扩展 CSS2.1。  
> 它为我们带来了许多期待已久的新特性，例如圆角，阴影，gradients(渐变)，transitions(过渡) 或 animations(动画) ， 当然还有新的布局如：multi-columns ， flexible box 或 grid layouts。

二、选择器
-----

CSS3 中，相对于 CSS2.1 版本的 7 个选择器，增加了更多其他的选择器，实现了更多的选择方式。

```
CSS2.1中，选择器7种：
id选择器        #box {}
类选择器        .red {}
标签选择器      p {}
后代            div p {}
交集            div.red {}
并集            div,p {}
通配符          * {}
```

### 2.1 关系选择符

> **\>** **_儿子，亲儿子，不是后代，必须是儿子_**  
> **+** **_next sibling，下一个兄弟_**  
> **~** **_next all siblings ，下所有兄弟_**

### 2，1.1 子级选择器

子级选择器用于选取带有特定父元素的元素。 书写语法：element1 > element2 意：如果 element2 元素不是父元素 element1 的直接子元素，则不会被选择。 > 号之前书写父级的选择器，> 符号之后写子级选择器，必须满足父子级关系才能选中签。

```
> 儿子选择器   IE7开始兼容
.box>p{
    color:red;
}
```

### 2.1.2 兄弟选择器


### 相邻兄弟选择器

```
相邻兄弟选择器可以用于选择紧接在另一个元素后的兄弟元素，而且二者有相同的父元素。    
书写语法：E1 + E2。
 
注意： a）选中的是紧跟在 E1 之后的同级元素 E2。 
      b）只能选中紧跟在后面的一个 E2 元素。 
      c）二者有相同的父元素。 
      d）+ 符号前后可以添加空格书写。

+ 下一个兄弟(相邻)，next sibling      IE7开始兼容
    h3+p{
        color:green;
    }

会变色的元素：
    <h3></h3>
    <p>●</p>    会变色
    <p>●</p>
    <p>●</p>
    <h3></h3>   
    <p>●</p>    会变色
    <p>●</p>
```

### 其他兄弟选择器

```
其他兄弟选择器匹配同一个父元素中在 element1 后面的所有 element2 元素。 
书写语法：element1~element2

注意： a）选择 element1 之后出现的所有 element2。 
       b）两种元素必须拥有相同的父元素，但是 element2 不必直接紧随      element1。 
       c）~ 符号前后可 以添加空格书写。

~ 后面所有兄弟，next all siblings
h3~p{
    color:red;
}

HTML结构中能够变红的：
<p>●</p>
<h3></h3>
<p>●</p>        会变色
<p>●</p>        会变色
<h3></h3>
<h4></h4>
<p>●</p>        会变色
<p>●</p>        会变色
<div>
    <p>●</p>
</div>
```



```
$("div>p").animate({"width":656},454);
IE6也能够兼容

$("div>p")
    等价于
$("div").children("p")

$("div~p")
    等价于
$("div").nextAll("p")
```

### 2.2 属性选择器

哲学上讲，CSS2.1层面，只能通过id属性、class属性选择元素。CSS3中，可以通过任意属性选择元素了。

| 选择器 | 示例 | 示例说明 | CSS |
| --- | --- | --- | --- |
| [._class_](https://www.runoob.com/cssref/sel-class.html) | .intro | 选择所有class="intro"的元素 | 1 |
| [#_id_](https://www.runoob.com/cssref/sel-id.html) | #firstname | 选择所有id="firstname"的元素 | 1 |
| [\*](https://www.runoob.com/cssref/sel-all.html) | \* | 选择所有元素 | 2 |
| _[element](https://www.runoob.com/cssref/sel-element.html)_ | p | 选择所有<p>元素 | 1 |
| _[element,element](https://www.runoob.com/cssref/sel-element-comma.html)_ | div,p | 选择所有<div>元素和 <p> 元素 | 1 |
| [element_.class_](https://www.runoob.com/cssref/sel-element-class.html) | p.hometown | 选择所有 class="hometown" 的 <p> 元素 | 1 |
| [_element_ _element_](https://www.runoob.com/cssref/sel-element-element.html) | div p | 选择<div>元素内的所有<p>元素 | 1 |
| [_element_\>_element_](https://www.runoob.com/cssref/sel-element-gt.html) | div>p | 选择所有父级是 <div> 元素的 <p> 元素 | 2 |
| [_element_+_element_](https://www.runoob.com/cssref/sel-element-pluss.html) | div+p | 选择所有紧跟在 <div> 元素之后的第一个 <p> 元素 | 2 |
| [\[_attribute_\]](https://www.runoob.com/cssref/sel-attribute.html) | \[target\] | 选择所有带有target属性元素 | 2 |
| [\[_attribute_\=_value_\]](https://www.runoob.com/cssref/sel-attribute-value.html) | \[target=-blank\] | 选择所有使用target="-blank"的元素 | 2 |
| [\[_attribute_~=_value_\]](https://www.runoob.com/cssref/sel-attribute-value-contains.html) | \[title~=flower\] | 选择标题属性包含单词"flower"的所有元素 | 2 |
| [\[_attribute_|=_language_\]](https://www.runoob.com/cssref/sel-attribute-value-lang.html) | \[lang|=en\] | 选择 lang 属性等于 en，或者以 en- 为开头的所有元素 | 2 |
| [:link](https://www.runoob.com/cssref/sel-link.html) | a:link | 选择所有未访问链接 | 1 |
| [:visited](https://www.runoob.com/cssref/sel-visited.html) | a:visited | 选择所有访问过的链接 | 1 |
| [:active](https://www.runoob.com/cssref/sel-active.html) | a:active | 选择活动链接 | 1 |
| [:hover](https://www.runoob.com/cssref/sel-hover.html) | a:hover | 选择鼠标在链接上面时 | 1 |
| [:focus](https://www.runoob.com/cssref/sel-focus.html) | input:focus | 选择具有焦点的输入元素 | 2 |
| [:first-letter](https://www.runoob.com/cssref/sel-firstletter.html) | p:first-letter | 选择每一个<p>元素的第一个字母 | 1 |
| [:first-line](https://www.runoob.com/cssref/sel-firstline.html) | p:first-line | 选择每一个<p>元素的第一行 | 1 |
| [:first-child](https://www.runoob.com/cssref/sel-firstchild.html) | p:first-child | 指定只有当<p>元素是其父级的第一个子级的样式。 | 2 |
| [:before](https://www.runoob.com/cssref/sel-before.html) | p:before | 在每个<p>元素之前插入内容 | 2 |
| [:after](https://www.runoob.com/cssref/sel-after.html) | p:after | 在每个<p>元素之后插入内容 | 2 |
| [:lang(_language_)](https://www.runoob.com/cssref/sel-lang.html) | p:lang(it) | 选择一个lang属性的起始值="it"的所有<p>元素 | 2 |
| [_element1_~_element2_](https://www.runoob.com/cssref/sel-gen-sibling.html) | p~ul | 选择p元素之后的每一个ul元素 | 3 |
| [\[_attribute_^=_value_\]](https://www.runoob.com/cssref/sel-attr-begin.html) | a\[src^="https"\] | 选择每一个src属性的值以"https"开头的元素 | 3 |
| [\[_attribute_$=_value_\]](https://www.runoob.com/cssref/sel-attr-end.html) | a\[src$=".pdf"\] | 选择每一个src属性的值以".pdf"结尾的元素 | 3 |
| [\[_attribute_\*=_value_\]](https://www.runoob.com/cssref/sel-attr-contain.html) | a\[src\*="runoob"\] | 选择每一个src属性的值包含子字符串"runoob"的元素 | 3 |
| [:first-of-type](https://www.runoob.com/cssref/sel-first-of-type.html) | p:first-of-type | 选择每个p元素是其父级的第一个p元素 | 3 |
| [:last-of-type](https://www.runoob.com/cssref/sel-last-of-type.html) | p:last-of-type | 选择每个p元素是其父级的最后一个p元素 | 3 |
| [:only-of-type](https://www.runoob.com/cssref/sel-only-of-type.html) | p:only-of-type | 选择每个p元素是其父级的唯一p元素 | 3 |
| [:only-child](https://www.runoob.com/cssref/sel-only-child.html) | p:only-child | 选择每个p元素是其父级的唯一子元素 | 3 |
| [:nth-child(_n_)](https://www.runoob.com/cssref/sel-nth-child.html) | p:nth-child(2) | 选择每个p元素是其父级的第二个子元素 | 3 |
| [:nth-last-child(_n_)](https://www.runoob.com/cssref/sel-nth-last-child.html) | p:nth-last-child(2) | 选择每个p元素的是其父级的第二个子元素，从最后一个子项计数 | 3 |
| [:nth-of-type(_n_)](https://www.runoob.com/cssref/sel-nth-of-type.html) | p:nth-of-type(2) | 选择每个p元素是其父级的第二个p元素 | 3 |
| [:nth-last-of-type(_n_)](https://www.runoob.com/cssref/sel-nth-last-of-type.html) | p:nth-last-of-type(2) | 选择每个p元素的是其父级的第二个p元素，从最后一个子项计数 | 3 |
| [:last-child](https://www.runoob.com/cssref/sel-last-child.html) | p:last-child | 选择每个p元素是其父级的最后一个子级。 | 3 |
| [:root](https://www.runoob.com/cssref/sel-root.html) | :root | 选择文档的根元素 | 3 |
| [:empty](https://www.runoob.com/cssref/sel-empty.html) | p:empty | 选择每个没有任何子级的p元素（包括文本节点） | 3 |
| [:target](https://www.runoob.com/cssref/sel-target.html) | #news:target | 选择当前活动的#news元素（包含该锚名称的点击的URL） | 3 |
| [:enabled](https://www.runoob.com/cssref/sel-enabled.html) | input:enabled | 选择每一个已启用的输入元素 | 3 |
| [:disabled](https://www.runoob.com/cssref/sel-disabled.html) | input:disabled | 选择每一个禁用的输入元素 | 3 |
| [:checked](https://www.runoob.com/cssref/sel-checked.html) | input:checked | 选择每个选中的输入元素 | 3 |
| [:not(_selector_)](https://www.runoob.com/cssref/sel-not.html) | :not(p) | 选择每个并非p元素的元素 | 3 |
| [::selection](https://www.runoob.com/cssref/sel-selection.html) | ::selection | 匹配元素中被用户选中或处于高亮状态的部分 | 3 |
| [:out-of-range](https://www.runoob.com/cssref/sel-out-of-range.html) | :out-of-range | 匹配值在指定区间之外的input元素 | 3 |
| [:in-range](https://www.runoob.com/cssref/sel-in-range.html) | :in-range | 匹配值在指定区间之内的input元素 | 3 |
| [:read-write](https://www.runoob.com/cssref/sel-read-write.html) | :read-write | 用于匹配可读及可写的元素 | 3 |
| [:read-only](https://www.runoob.com/cssref/sel-read-only.html) | :read-only | 用于匹配设置 "readonly"（只读） 属性的元素 | 3 |
| [:optional](https://www.runoob.com/cssref/sel-optional.html) | :optional | 用于匹配可选的输入元素 | 3 |
| [:required](https://www.runoob.com/cssref/sel-required.html) | :required | 用于匹配设置了 "required" 属性的元素 | 3 |
| [:valid](https://www.runoob.com/cssref/sel-valid.html) | :valid | 用于匹配输入值为合法的元素 | 3 |
| [:invalid](https://www.runoob.com/cssref/sel-invalid.html) | :invalid | 用于匹配输入值为非法的元素 | 3 |


三、伪类
----

CSS2.1中，只能给a标签增加伪类。a:link、a:hover、a:visited、a:active。

### 3.1 :hover能够给所有元素使用了

> :hover这个选择器，在CSS3中，能够给任何元素使用了。 IE7兼容各种元素:hover

### 3.2 :focus得到焦点时

> 当一个表单元素有焦点，那么就能够被 :focus伪类选中。  
> input:focus{  
> /\*动画\*/  
> animation:haha 1s ease 0s infinite alternate;  
> }

### 3.3 :not反着选

> 没有.haha类的p，IE9兼容  
> p:not(.haha)

### 3.4 :only-child 唯一的儿子

> 如果一个p是某一个元素的唯一的儿子，那么选择它。IE9兼容。  
> p:only-child {  
> color:red;  
> }

### 3.5 :empty 空标签

> _当一个标签是完全首尾相接，没有任何的空格、tab、换行、文字，就是:empty_  
>   
> <div></div> → 满足div:empty  
> <div> </div>  
> <div>  
>   
> </div>  
> <div>我</div>

### 3.6 :checked 选中的

> 单选按钮、复选框，如果被勾选，那么能被伪类:checked选中  
> input\[type=”radio”\]:checked

### 3.7 :disabled和:enabled

> IE9兼容  
> 无效和有效的input控件。  
> <input type="text" disabled/>  
> <input type="text" />  
>   
> <input type="button" disabled value="adsfdsaf"/>  
> <input type="button" value="adsfdsaf"/>  
>   
> input:disabled

### 3.8 结构伪类选择器

![](https://pic1.zhimg.com/v2-c3845d24e3f0983ce2ac3ed4eded379c_r.jpg)

### _nth-child（n）_

> • n 可以是数字，关键字和公式  
> • n 如果是数字，就是选择第 n 个  
> • 常见的关键词 even 偶数 odd 奇数  
> • 常见的公式如下 ( 如果 n 是公式，则从 0 开始计算，n是从 0 ，1，2，3.. 一直递增）  
> • 但是第 0 元素或者超出了元素的个数会被忽略

![](https://pic3.zhimg.com/v2-91977e6cf372bac1a0ebd43efd4e47fe_r.jpg)

### **_E:nth-child(n)_ 和 _E:nth-of-type(n)_ 的区别**

> • E:nth-child(n) 匹配父元素的第 n 个子元素 E，同时需要满足两个条件。  
> • E:nth-of-type(n) 匹配同类型中的第 n 个同级兄弟元素 E，会忽视其他同级的非同类型元  
> 素。

![](https://pic4.zhimg.com/v2-c7162a605d36c3c1c9cb391482713017_r.jpg)

  

四、伪元素
-----

新增伪元素

![](https://pic1.zhimg.com/v2-ad2376b703ab9606004f60331454f2f4_r.jpg)

### 4.1 ::before 、 ::after

> 两个冒号表示伪元素。  
> p::before{  
> content:">>>>";  
> }  
>   
> content表示内容，所有的 ::before 必须有content属性，否则语法错误。  
> 如果没有content，那么也要写content:""  
> 注意 ::before 、::after都是行内元素，必须转块或者脱标才能设置宽度高度。

before的诞生，方便了很多：

![](data:image/svg+xml;utf8,<svg xmlns='http://www.w3.org/2000/svg' width='280' height='184'></svg>)

> **_after可以用来清除浮动。_**  
> .cl::after{  
> content:"";  
> display: block;  
> clear: both;  
> }

### IE8不兼容::after，但是兼容:after。所以为了更大的兼容，写成:after即可。

### 4.2 ::selection 被选中的文字样式

> p::selection{  
> background-color: orange;  
> color:white;  
> }


IE9开始兼容

### h5 写法和传统写法区别

> • 1. 单冒号 E:before  
> • 2. 双冒号 E::before  
> _**• 浏览器对以上写法都能识别，双冒号是 h5 的语法规范。**_

### 伪元素的注意事项

> • _**伪元素只能给双标签添加，不能给单标签添加**_  
> • 伪元素的冒号前不能有空格，如 E ::before 这个写法是错误的  
> • 伪元素里面必须写上属性 content:"";  
> • _**before 和 after 创建一个元素，但是属于行内元素**_  
> • 因为在 DOM 里面看不见刚才创建的元素，所以我们称为伪元素。

### 选择器权重

> **_• 基础选择器：id 选择器 > 类选择器 > 标签选择器 > \*_**  
> **_• 伪类选择器、属性选择器 的权重等于类选择器 。_**  
> **_• 伪元素选择器 的权重等于标签选择器 。_**
