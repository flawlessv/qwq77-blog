---
title: SASS笔记
tags:
  - SASS
# categories:
#   - 前端
---



SASS语法嵌套规则与注释

 
语法嵌套规则

 
选择器嵌套

例如有这么一段css，正常CSS的写法

.container{width:1200px; margin: 0 auto;}

.container .header{height: 90px; line-height: 90px;}

.container .header .log{width:100px; height:60px;}

.container .center{height: 600px; background-color: #F00;}

.container .footer{font-size: 16px;text-align: center;}

改成写SASS的方法

.container {

    width: 1200px;

    margin: 0 auto;

    .header {

        height: 90px;

        line-height: 90px;

        .log {

            width: 100px;

            height: 60px;

        }

    }

    .center {

        height: 600px;

        background-color: #F00;

    }

    .footer {

        font-size: 16px;

        text-align: center;

    }

}

避免了重复输入父选择器，复杂的 CSS 结构更易于管理

 
父选择器 &

在嵌套 CSS 规则时，有时也需要直接使用嵌套外层的父选择器，例如，当给某个元素设定 hover 样式时，或者当 body 元素有某个 classname 时，可以用 & 代表嵌套规则外层的父选择器。

例如有这么一段样式：

.container{width: 1200px;margin: 0 auto;}

.container a{color: #333;}

.container a:hover{text-decoration: underline;color: #F00;}

.container .top{border:1px #f2f2f2 solid;}

.container .top-left{float: left; width: 200px;} 

用sass编写

.container {

    width: 1200px;

    margin: 0 auto;

    a {

        color: #333;

        &:hover {

            text-decoration: underline;

            color: #F00;

        }

    }

    .top {

        border: 1px #f2f2f2 solid;

        &-left {

            float: left;

            width: 200px;

        }

    }

}

 

 
属性嵌套

有些 CSS 属性遵循相同的命名空间 (namespace)，比如 font-family, font-size, font-weight 都以 font 作为属性的命名空间。为了便于管理这样的属性，同时也为了避免了重复输入，Sass 允许将属性嵌套在命名空间中

例如：

.container a {

    color: #333;

    font-size: 14px;

    font-family: sans-serif;

    font-weight: bold;

}

用SASS的方式写

.container {

    a {

        color: #333;

        font: {

            size: 14px;

            family: sans-serif;

            weight: bold;

        }

    }

}

注意font：后面要加一个空格

 
占位符选择器 %foo 必须通过 @extend

有时，需要定义一套样式并不是给某个元素用，而是只通过 @extend 指令使用，尤其是在制作 Sass 样式库的时候，希望 Sass 能够忽略用不到的样式。

例如：

.button%base {

    display: inline-block;

    margin-bottom: 0;

    font-weight: normal;

    text-align: center;

    white-space: nowrap;

    vertical-align: middle;

    -ms-touch-action: manipulation;

    touch-action: manipulation;

    cursor: pointer;

    background-image: none;

    border: 1px solid transparent;

    padding: 6px 12px;

    font-size: 14px;

    line-height: 1.42857143;

    border-radius: 4px;

    -webkit-user-select: none;

    -moz-user-select: none;

    -ms-user-select: none;

    user-select: none;

}


.btn-default {

    @extend %base;

    color: #333;

    background-color: #fff;

    border-color: #ccc;

}


.btn-success {

    @extend %base;

    color: #fff;

    background-color: #5cb85c;

    border-color: #4cae4c;

}


.btn-danger {

    @extend %base;

    color: #fff;

    background-color: #d9534f;

    border-color: #d43f3a;

}

 

 
注释

 

Sass支持两种注释

    标准的css多行注释 /* ... */			会编译到.css文件中
    单行注释 //						不会编译到.css文件

.container {

    width: 1200px;

    .swiper {

        // 网站幻灯片相关css

        width: 100%;

        height: 260px;

        .dot {

            /* 

                    幻灯片指示点

                    默认白色

                    选中时蓝色

                */

            width: 10px;

            height: 10px;

            border-radius: 50%;

            background-color: #FFF;

            &.active {

                background-color: blue;

            }

        }

    }

}

 

 
SASS变量

 
css变量的定义与书写

 
CSS定义变量的方法

:root {

    --color: #F00;

}


body {

    --border-color: #f2f2f2;

}


.header {

    --background-color: #f8f8f8;

}


p {

    color: var(--color);

    border-color: var(--border-color);

}


.header {

    background-color: var(--background-color);

}

SASS的写法

$font-size:14px;

.container {

    font-size: $font-size;

}

 

 
Sass变量的定义

 
定义规则

    变量以美元符号($)开头，后面跟变量名；
    变量名是不以数字开头的可包含字母、数字、下划线、横线（连接符）；
    写法同css，即变量名和值之间用冒号(:)分隔；
    变量一定要先定义，后使用；

 
连接符与下划线

通过连接符与下划线 定义的同名变量为同一变量，建议使用连接符

$font-size:14px;

$font_size:16px;

.container{font-size: $font-size;}

 
变量的作用域
局部变量

定义：在选择器内容定义的变量，只能在选择器范围内使用

.container {

    $font-size: 14px;

    font-size: $font-size;

}

 
全局变量

定义后能全局使用的变量
第一种：在选择器外面的最前面定义的变量

$font-size:16px;

.container {

    font-size: $font-size;

}

.footer {

    font-size: $font-size;

}

第二种：使用 !global 标志定义全局变量

.container {

    $font-size: 16px !global;

    font-size: $font-size;

}

.footer {

    font-size: $font-size;

}

 
变量值类型

变量值的类型可以有很多种

SASS支持 7 种主要的数据类型

    数字，1, 2, 13, 10px，30%
    字符串，有引号字符串与无引号字符串，"foo", 'bar', baz
    颜色，blue, #04a3f9, rgba(255,0,0,0.5)
    布尔型，true, false
    空值，null
    数组 (list)，用空格或逗号作分隔符，1.5em 1em 0 2em, Helvetica, Arial, sans-serif
    maps, 相当于 JavaScript 的 object，(key1: value1, key2: value2)

 

例如

$layer-index:10;

$border-width:3px;

$font-base-family:'Open Sans', Helvetica, Sans-Serif;

$top-bg-color:rgba(255,147,29,0.6);

$block-base-padding:6px 10px 6px 10px;

$blank-mode:true;

$var:null; // 值null是其类型的唯一值。它表示缺少值，通常由函数返回以指示缺少结果。

$color-map: (color1: #fa0000, color2: #fbe200, color3: #95d7eb);


$fonts: (serif: "Helvetica Neue",monospace: "Consolas");

使用

.container {

    $font-size: 16px !global;

    font-size: $font-size;

    @if $blank-mode {

        background-color: #000;

    }

    @else {

        background-color: #fff;

    }

    content: type-of($var);

    content:length($var);

    color: map-get($color-map, color2);

}


.footer {

    font-size: $font-size;

}


// 如果列表中包含空值，则生成的CSS中将忽略该空值。

.wrap {

    font: 18px bold map-get($fonts, "sans");

}

 
默认值

$color:#333;

// 如果$color之前没定义就使用如下的默认值

$color:#666 !default;

.container {

    border-color: $color;

}

 
SASS 导入@import

 
@import

Sass 拓展了 @import 的功能，允许其导入 SCSS 或 Sass 文件。被导入的文件将合并编译到同一个 CSS 文件中，另外，被导入的文件中所包含的变量或者混合指令 (mixin) 都可以在导入的文件中使用。

例如

public.scss

$font-base-color:#333;

在index.scss里面使用

@import "public";

$color:#666;

.container {

    border-color: $color;

    color: $font-base-color;

}

注意：跟我们普通css里面@import的区别

 
如下几种方式，都将作为普通的 CSS 语句，不会导入任何 Sass 文件

    文件拓展名是 .css；
    文件名以 http:// 开头；
    文件名是 url()；
    @import 包含 media queries。

@import "public.css";

@import url(public);

@import "http://xxx.com/xxx";

@import 'landscape' screen and (orientation:landscape);

 

 
局部文件(Partials)

Sass源文件中可以通过@import指令导入其他Sass源文件，被导入的文件就是*局部文件*，局部文件让Sass模块化编写更加容易。

如果一个目录正在被Sass程序监测，目录下的所有scss/sass源文件都会被编译，但通常不希望局部文件被编译，因为局部文件是用来被导入到其他文件的。如果不想局部文件被编译，文件名可以以下划线 （_）开头

例如：

_theme.scss

$border-color:#999;

$background-color:#f2f2f2;

使用

@import "theme";

.container {

    border-color: $border-color;

    background-color: $background-color;

}

可以看到，@import 引入的theme.scss，可以没有，这是允许的，这也就意味着，同一个目录下不能同时出现两个相关名的sass文件（一个不带，一个带），添加下划线的文件将会被忽略。

 

 
嵌套 @import

大多数情况下，一般在文件的最外层（不在嵌套规则内）使用 @import，其实，也可以将 @import 嵌套进 CSS 样式或者 @media 中，与平时的用法效果相同，只是这样导入的样式只能出现在嵌套的层中。

例如

_base.scss

.main-color {

    color: #F00;

}

使用

.container {

    @import "base";

}

 

注意：@import不能嵌套使用在控制指令或混入中

 
SASS混合指令 (Mixin Directives)

	混合指令（Mixin）用于定义可重复使用的样式。混合指令可以包含所有的 CSS 规则，绝大部分 Sass 规则，甚至通过参数功能引入变量，输出多样化的样式。

 
定义与使用混合指令 @mixin

@mixin mixin-name() {

    /* css 声明 */

}

例1：标准形式

定义

// 定义页面一个区块基本的样式

@mixin block {

    width: 96%;

    margin-left: 2%;

    border-radius: 8px;

    border: 1px #f6f6f6 solid;

}

使用

// 使用混入

.container {

    .block {

        @include block;

    }

}

 
例2：嵌入选择器

例如

// 定义警告字体样式,下划线（_）与横线（-）是一样的

@mixin warning-text {

    .warn-text {

        font-size: 12px;

        color: rgb(255, 253, 123);

        line-height: 180%;

    }

}

使用

// 使用混入

.container {

    @include warning-text;

}

 
例3：使用变量

定义

// 定义flex布局元素纵轴的排列方式

@mixin flex-align($aitem) {

    -webkit-box-align: $aitem;

    -webkit-align-items: $aitem;

    -ms-flex-align: $aitem;

    align-items: $aitem;

}

使用

// 只有一个参数，直接传递参数

.container {

    @include flex-align(center);

}


// 给指定参数指定值

.footer {

    @include flex-align($aitem: center);

}

 
例4：使用变量（多参数）

例如

// 定义块元素内边距

@mixin block-padding($top, $right, $bottom, $left) {

    padding-top: $top;

    padding-right: $right;

    padding-bottom: $bottom;

    padding-left: $left;

}

使用一

// 按照参数顺序赋值

.container {

    @include block-padding(10px, 20px, 30px, 40px);

}

使用二

// 可指定参数赋值

.container {

    @include block-padding($left: 20px, $top: 10px, $bottom: 10px, $right: 30px);

}

使用三：只设置两边

// 可指定参数赋值

.container {

    @include block-padding($left: 10px, $top: 10px, $bottom: 0, $right: 0);

}

问题：必须指定4个值

 
例5：指定默认值

定义

// 定义块元素内边距，参数指定默认值

@mixin block-padding($top:0, $right:0, $bottom:0, $left:0) {

    padding-top: $top;

    padding-right: $right;

    padding-bottom: $bottom;

    padding-left: $left;

}

使用

// 可指定参数赋值

.container {

    // 不带参数

    //@include block-padding;

    //按顺序指定参数值

    //@include block-padding(10px,20px);

    //给指定参数指定值

    @include block-padding($left: 10px, $top: 20px)

}

例6：可变参数

参数不固定的情况

/** 

    *定义线性渐变

    *@param $direction  方向

    *@param $gradients  颜色过度的值列表

 */


@mixin linear-gradient($direction, $gradients...) {

    background-color: nth($gradients, 1);

    background-image: linear-gradient($direction, $gradients);

}

使用

.table-data {

    @include linear-gradient(to right, #F00, orange, yellow);

}

 
@mixin混入总结

    mixin是可以重复使用的一组CSS声明
    mixin有助于减少重复代码，只需声明一次，就可在文件中引用
    混合指令可以包含所有的 CSS 规则，绝大部分 Sass 规则，甚至通过参数功能引入变量，输出多样化的样式。
    使用参数时建议加上默认值

 

什么时候用？？？？ 很多地方都会用到却能根据不同场景灵活使用的样式

 
SASS @extend（继承）指令

	在设计网页的时候通常遇到这样的情况：一个元素使用的样式与另一个元素完全相同，但又添加了额外的样式。通常会在 HTML 中给元素定义两个 class，一个通用样式，一个特殊样式。

image-20211127090211485

 
CSS案例

接下来以警告框为例进行讲解4种类型
标记	说明
info	信息！请注意这个信息。
success	成功！很好地完成了提交。
warning	警告！请不要提交。
danger	错误！请进行一些更改。

所有警告框的基本样式（风格、字体大小、内边距、边框等...） ，因为我们通常会定义一个通用alert样式

.alert {

    padding: 15px;

    margin-bottom: 20px;

    border: 1px solid transparent;

    border-radius: 4px;

    font-size: 12px;

}

不同警告框单独风格

.alert-info {

    color: #31708f;

    background-color: #d9edf7;

    border-color: #bce8f1;

}


.alert-success {

    color: #3c763d;

    background-color: #dff0d8;

    border-color: #d6e9c6;

}


.alert-warning {

    color: #8a6d3b;

    background-color: #fcf8e3;

    border-color: #faebcc;

}


.alert-danger {

    color: #a94442;

    background-color: #f2dede;

    border-color: #ebccd1;

}

使用

<div class="alert alert-info">

    信息！请注意这个信息。

</div>


<div class="alert alert-success">

    成功！很好地完成了提交。

</div>


<div class="alert alert-warning">

    警告！请不要提交。

</div>


<div class="alert alert-danger">

    错误！请进行一些更改。

</div>

 
使用继承@extend改进

基本样式我们没有变，主要是各个警告框单独的样式

.alert-info {

    @extend .alert;

    color: #31708f;

    background-color: #d9edf7;

    border-color: #bce8f1;

}


.alert-success {

    @extend .alert;

    color: #3c763d;

    background-color: #dff0d8;

    border-color: #d6e9c6;

}


.alert-warning {

    @extend .alert;

    color: #8a6d3b;

    background-color: #fcf8e3;

    border-color: #faebcc;

}


.alert-danger {

    @extend .alert;

    color: #a94442;

    background-color: #f2dede;

    border-color: #ebccd1;

}

使用时就不须要再写基本类了

<div class="alert-info">

    信息！请注意这个信息。

</div>


<div class="alert-success">

    成功！很好地完成了提交。

</div>


<div class="alert-warning">

    警告！请不要提交。

</div>


<div class="alert-danger">

    错误！请进行一些更改。

</div>

 
使用多个@extend

定义两个类

.alert {

    padding: 15px;

    margin-bottom: 20px;

    border: 1px solid transparent;

    border-radius: 4px;

    font-size: 12px;

}


.important {

    font-weight: bold;

    font-size: 14px;

}

使用

.alert-danger {

    @extend .alert;

    @extend .important;

    color: #a94442;

    background-color: #f2dede;

    border-color: #ebccd1;

}

 
@extend多层继承

第一层继承

.alert {

    padding: 15px;

    margin-bottom: 20px;

    border: 1px solid transparent;

    border-radius: 4px;

    font-size: 12px;

}


.important {

    @extend .alert;

    font-weight: bold;

    font-size: 14px;

}

再继承

.alert-danger {

    @extend .important;

    color: #a94442;

    background-color: #f2dede;

    border-color: #ebccd1;

}

 
占位符%

你可能发现被继承的css父类并没有被实际应用，也就是说html代码中没有使用该类，它的唯一目的就是扩展其他选择器。

对于该类，可能不希望被编译输出到最终的css文件中，它只会增加CSS文件的大小，永远不会被使用。

这就是占位符选择器的作用。

占位符选择器类似于类选择器，但是，它们不是以句点(.)开头，而是以百分号(%)开头。

当在Sass文件中使用占位符选择器时，它可以用于扩展其他选择器，但不会被编译成最终的CSS。

改写

%alert {

    padding: 15px;

    margin-bottom: 20px;

    border: 1px solid transparent;

    border-radius: 4px;

    font-size: 12px;

}


.alert-info {

    @extend %alert;

    color: #31708f;

    background-color: #d9edf7;

    border-color: #bce8f1;

}


.alert-success {

    @extend %alert;

    color: #3c763d;

    background-color: #dff0d8;

    border-color: #d6e9c6;

}


.alert-warning {

    @extend %alert;

    color: #8a6d3b;

    background-color: #fcf8e3;

    border-color: #faebcc;

}


.alert-danger {

    @extend %alert;

    color: #a94442;

    background-color: #f2dede;

    border-color: #ebccd1;

}

还可以用@mixin，@import等实现并改进

@import      导入局部模块化样式（类似功能、同一组件）	  多次导入

@minix	  定义可重复使用的样式

 
SASS 运算 (Operations)符的基本使用

 
等号操作符

所有数据类型都支持等号运算符:
符号	说明
==	等于
!=	不等于

例1数字比较：

$theme:1;

.container {

    @if $theme==1 {

        background-color: red;

    }

    @else {

        background-color: blue;

    }

}

例2字符串比较：

$theme:"blue";

.container {

    @if $theme !="blue" {

        background-color: red;

    }

    @else {

        background-color: blue;

    }

}

所有数据类型均支持相等运算 == 或 !=，此外，每种数据类型也有其各自支持的运算方式。

 
关系（比较）运行符

 
符号	说明
< （lt）	小于
>     （gt）	大于
<= （lte）	小于等于
>=   （gte）	大于等于

例

$theme:3;

.container {

    @if $theme >= 5 {

        background-color: red;

    }

    @else {

        background-color: blue;

    }

}

逻辑运行符

 
符号	说明
and	逻辑与
or	逻辑或
not	逻辑非

例

$width:100;

$height:200;

$last:false;

div {

    @if $width>50 and $height<300 {

        font-size: 16px;

    }

    @else {

        font-size: 14px;

    }

    @if not $last {

        border-color: red;

    }

    @else {

        border-color: blue;

    }

}

 
数字操作符
符号	说明
+	加
-	减
*	乘
/	除
%	取模

例

/* 

    +、-、*、/、%

    线数字、百分号、css部分单位（px、pt、in...）

    +

    线数字与百分号或单位运算时会自动转化成相应的百分比与单位值

*/

.container {

    /* ==================+ 运算===================== */

    width: 50 + 20;

    width: 50 + 20%;

    width: 50% + 20%;

    width: 10px + 20px;

    width: 10pt + 20px;

    width: 10pt + 20;

    width: 10px + 10;

    /* ==================- 运算===================== */

    height: 50 - 30;

    height: 10 - 30%;

    height: 60% - 30%;

    height: 50px - 20px;

    height: 50pt - 20px;

    height: 50pt - 40;

    /* ==================* 运算===================== */

    height: 50 * 30;

    height: 10 * 30%;

    /* height: 60% * 30%; 出现了两个百分号*/

    /* height: 50px * 20px; 出现了两个单位*/

    height: 50 * 2px;

    height: 50pt * 4;

    /* ==================/运算 (除完后最多只能保留一种单位)===================== */

    $width: 100px;

    width: 10 / 5;

    width: 10px / 5px;

    width: 10px / 10 * 2;

    width: 20px / 2px * 5%;

    width: ($width/2); // 使用变量与括号

    z-index: round(10)/2; // 使用了函数

    height: (500px/2); // 使用了括号

    /* ==================% 运算===================== */

    width: 10 % 3;

    width: 50 % 3px;

    width: 50px % 4px;

    width: 50px % 7;

    width: 50% % 7;

    width: 50% % 9%;

    width: 50px % 10pt; // 50px % 13.33333px  

    width: 50px % 13.33333px;

    width: 50px + 10pt;

    /* width: 50px % 5%; 单位不统一*/

}

 

/ 在 CSS 中通常起到分隔数字的用途，SassScript 作为 CSS 语言的拓展当然也支持这个功能，同时也赋予了 / 除法运算的功能。也就是说，如果 / 在 SassScript 中把两个数字分隔，编译后的 CSS 文件中也是同样的作用。

 

以下三种情况 / 将被视为除法运算符号：

    如果值或值的一部分，是变量或者函数的返回值
    如果值被圆括号包裹
    如果值是算数表达式的一部分

 

例

$width: 1000px;

div {

    font: 16px/30px Arial, Helvetica, sans-serif; // 不运算

    width: ($width/2); // 使用变量与括号

    z-index: round(10)/2; // 使用了函数

    height: (500px/2); // 使用了括号

    margin-left: 5px + 8px/2px; // 使用了+表达式

}

如果需要使用变量，同时又要确保 / 不做除法运算而是完整地编译到 CSS 文件中，只需要用 #{} 插值语句将变量包裹。

 
字符串运算

+ 可用于连接字符串

注意：如果有引号字符串（位于 + 左侧）连接无引号字符串，运算结果是有引号的，相反，无引号字符串（位于 + 左侧）连接有引号字符串，运算结果则没有引号。

有问题？？？？   如果有一个值是函数返回的，情况可能不一样

例如

.container {

    content: "Foo " + Bar;

    font-family: sans- + "serif";

}

 
SASS 插值语句 #{ }

引入之前的案例发出一个问题

例如

p{

    font: 16px/30px Arial, Helvetica, sans-serif; 

}

如果需要使用变量，同时又要确保 / 不做除法运算而是完整地编译到 CSS 文件中，只需要用 #{} 插值语句将变量包裹。

使用插值语法：

p {

    $font-size: 12px;

    $line-height: 30px;

    font: #{$font-size}/#{$line-height} Helvetica,

    sans-serif;

}

通过 #{} 插值语句可以在选择器、属性名、注释中使用变量：

$class-name: danger;

$attr: color;

$author:'老姚';


/* 

   * 这是文件的说明部分

    @author: #{\$author}

 */


a.#{$class-name} {

    border-#{$attr}: #F00;

}

sass 常见函数的基本使用

 

常见函数简介，更多函数列表可看：https://sass-lang.com/documentation/modules 

 
Color(颜色函数)

sass包含很多操作颜色的函数。例如：lighten() 与 darken()函数可用于调亮或调暗颜色，opacify()函数使颜色透明度减少，transparent()函数使颜色透明度增加，mix()函数可用来混合两种颜色。

p {

    height: 30px;

}


.p0 {

    background-color: #5c7a29;

}


.p1 {

    /* 

        让颜色变亮

        lighten($color, $amount)

        $amount 的取值在0% - 100% 之间

     */

    background-color: lighten(#5c7a29, 30%);

}


.p2 {

    // 让颜色变暗  通常使用color.scale()代替该方案

    background-color: darken(#5c7a29, 15%);

}


.p3 {

    // 降低颜色透明度  通常使用color.scale()代替该方案

    // background-color: opacify(#5c7a29,0.5);

    background-color: opacify(rgba(#5c7a29, 0.1), 0.5);

}

使用

<p></p>

<p class="p0"></p>

<p class="p1"></p>

<p class="p2"></p>

<p class="p3"></p>

 
String（字符串函数）

Sass有许多处理字符串的函数，比如向字符串添加引号的quote()、获取字符串长度的string-length()和将内容插入字符串给定位置的string-insert()。

例

p {

    &:after {

        content: quote(这是里面的内容);

    }

    background-color: unquote($string: "#F00");

    z-index:str-length("sass学习");

}

 
Math(数值函数)

数值函数处理数值计算，例如：percentage()将无单元的数值转换为百分比，round()将数字四舍五入为最接近的整数，min()和max()获取几个数字中的最小值或最大值，random()返回一个随机数。

例如

p {

    z-index: abs($number: -15); // 15

    z-index: ceil(5.8); //6

    z-index: max(5, 1, 6, 8, 3); //8

    opacity: random(); // 随机 0-1

}

 
List函数

List函数操作List，length()返回列表长度，nth()返回列表中的特定项，join()将两个列表连接在一起，append()在列表末尾添加一个值。

例如：

p {

    z-index: length(12px); //1

    z-index: length(12px 5px 8px); //3

    z-index: index(a b c d, c); //3

    padding: append(10px 20px, 30px); // 10px 20px 30px

    color: nth($list: red blue green, $n: 2); // blue

}

 
Map函数

Map函数操作Map，map-get()根据键值获取map中的对应值，map-merge()来将两个map合并成一个新的map，map-values()映射中的所有值。

$font-sizes: ("small": 12px, "normal": 18px, "large": 24px);

$padding:(top:10px, right:20px, bottom:10px, left:30px);

p {

    font-size: map-get($font-sizes, "normal"); //18px

    @if map-has-key($padding, "right") {

        padding-right: map-get($padding, "right");

    }

    &:after {

        content: map-keys($font-sizes) + " "+ map-values($padding) + "";

    }

}

 
selector选择器函数

	选择符相关函数可对CSS选择进行一些相应的操作，例如：selector-append()可以把一个选择符附加到另一个选择符，selector-unify()将两组选择器合成一个复合选择器。

例如

.header {

    background-color: #000;

    content: selector-append(".a", ".b", ".c") + '';

    content: selector-unify("a", ".disabled") + '';

}

 
自检函数

	自检相关函数，例如：feature-exists()检查当前Sass版本是否存在某个特性，variable-exists()检查当前作用域中是否存在某个变量，mixin-exists()检查某个mixin是否存在。

例如：

$color:#F00;

@mixin padding($left:0, $top:0, $right:0, $bottom:0) {

    padding: $top $right $bottom $left;

}


.container {

    @if variable-exists(color) {

        color: $color;

    }

    @else {

        content: "$color不存在";

    }

    @if mixin-exists(padding) {

        @include padding($left: 10px, $right: 10px);

    }

}

自检函数通常用在代码的调试上
sass 流程控制指令@if、@for、@each、@while

 
@if控制指令

@if()函数允许您根据条件进行分支，并仅返回两种可能结果中的一种。

语法方式同js的if....else if ...else

看流程图

代码形式：

.container{

    // 第一种

    @if(/* 条件 */){

        // ...

    }


    // 第二种

    @if(/* 条件 */){

        // ...

    }@else{

        // ...

    }

    

    // 第三种

    @if(/* 条件 */){

        // ...

    }@else if(){

        // ...

    }@else{

        // ...

    }

}

例1

$theme:"green";

.container {

    @if $theme=="red" {

        color: red;

    }

    @else if $theme=="blue" {

        color: blue;

    }

    @else if $theme=="green" {

        color: green;

    }

    @else {

        color: darkgray;

    }

}

例如，定义一个css的三角形@mixin声明

@mixin triangle($direction:top, $size:30px, $border-color:black) {

    width: 0px;

    height: 0px;

    display: inline-block;

    border-width: $size;

    border-#{$direction}-width: 0;

    @if ($direction==top) {

        border-color: transparent transparent $border-color transparent;

        border-style: dashed dashed solid dashed;

    }

    @else if($direction==right) {

        border-color: transparent transparent transparent $border-color;

        border-style: dashed dashed dashed solid;

    }

    @else if($direction==bottom) {

        border-color: $border-color transparent transparent transparent;

        border-style: solid dashed dashed dashed;

    }

    @else if($direction==left) {

        border-color: transparent $border-color transparent transparent;

        border-style: dashed solid dashed dashed;

    }

}

使用

.p0 {

    @include triangle();

}


.p1 {

    @include triangle(right, 50px, red);

}


.p2 {

    @include triangle(bottom, 50px, blue);

}


.p3 {

    @include triangle(left, 50px, green);

}

html

<p class="p0"></p>

<p class="p1"></p>

<p class="p2"></p>

<p class="p3"></p>

 
@for指令

@for 指令可以在限制的范围内重复输出格式，每次按要求（变量的值）对输出结果做出变动。这个指令包含两种格式：@for $var from  through ，或者 @for $var from  to 

区别在于 through 与 to 的含义：

    当使用through时，条件范围包含与的值。
    而使用to 时条件范围只包含的值不包含  的值。
    另外，$var 可以是任何变量，比如 $i； 和  必须是整数值。

例1

@for $i from 1 to 4 {

    .p#{$i} {

        width: 10px * $i;

        height: 30px;

        background-color: red;

    }

}


@for $i from 1 through 3 {

    .p#{$i} {

        width: 10px * $i;

        height: 30px;

        background-color: red;

    }

}

使用

<p class="p1"></p>

<p class="p2"></p>

<p class="p3"></p>

 

例2：加载动画

#loading {

    position: fixed;

    top: 200px;

    left: 46%;

}


#loading span {

    position: absolute;

    width: 20px;

    height: 20px;

    background: #3498db;

    opacity: 0.5;

    border-radius: 50%;

    animation: loading 1s infinite ease-in-out;

}


#loading span:nth-child(1) {

    left: 0;

    animation-delay: 0s;

}


#loading span:nth-child(2) {

    left: 20px;

    animation-delay: 0.2s;

}


#loading span:nth-child(3) {

    left: 40px;

    animation-delay: 0.4s;

}


#loading span:nth-child(4) {

    left: 60px;

    animation-delay: 0.6s;

}


#loading span:nth-child(5) {

    left: 80px;

    animation-delay: .8s;

}


@keyframes loading {

    0% {

        opacity: 0.3;

        transform: translateY(0px);

    }

    50% {

        opacity: 1;

        transform: translateY(-20px);

        background: green;

    }

    100% {

        opacity: 0.3;

        transform: translateY(0px);

    }

}

html

<div id="loading">

    <span></span>

    <span></span>

    <span></span>

    <span></span>

    <span></span>

</div>

用@for改进动画部分

@for $i from 1 to 5 {

    #loading span:nth-child(#{$i}) {

        left: 20 * ($i - 1) + px;

        /* animation-delay: 20 * ($i - 1) / 100 + s; */

        animation-delay: unquote($string: "0.") + ($i - 1) * 2 + s;

    }

}

 
@each指令

@each 指令的格式是 $var in , $var 可以是任何变量名，比如 $length 或者 $name，而  是一连串的值，也就是值列表。

例如做如下效果

image-20211129101633273

 

普通CSS的写法

p{

    width: 10px;

    height: 10px;

    display: inline-block;

    margin: 10px;

}

.p0{

    background-color: red;

}

.p1{

    background-color: green;

}

.p2{

    background-color: blue;

}


.p3{

    background-color:turquoise;

}


.p4{

    background-color: darkmagenta;

}

 

用@each改进

$color-list:red green blue turquoise darkmagenta;

@each $color in $color-list {

    $index: index($color-list, $color);

    .p#{$index - 1} {

        background-color: $color;

    }

}

 
@while 指令

@while 指令重复输出格式直到表达式返回结果为 false。这样可以实现比 @for 更复杂的循环。

用sass实现bootstrap中css的这么一段代码

https://stackpath.bootstrapcdn.com/bootstrap/3.4.1/css/bootstrap.css 

.col-sm-12 {

    width: 100%;

}


.col-sm-11 {

    width: 91.66666667%;

}


.col-sm-10 {

    width: 83.33333333%;

}


.col-sm-9 {

    width: 75%;

}


.col-sm-8 {

    width: 66.66666667%;

}


.col-sm-7 {

    width: 58.33333333%;

}


.col-sm-6 {

    width: 50%;

}


.col-sm-5 {

    width: 41.66666667%;

}


.col-sm-4 {

    width: 33.33333333%;

}


.col-sm-3 {

    width: 25%;

}


.col-sm-2 {

    width: 16.66666667%;

}


.col-sm-1 {

    width: 8.33333333%;

}

用@while实现

$column:12;

@while $column>0 {

    .col-sm-#{$column} {

        width: $column / 12 * 100%;

        // width: $column / 12 * 100 + %; 会标红

        width: $column / 12 * 100#{"%"};

        width: unquote($string: $column / 12 * 100 + "%");

    }

    $column:$column - 1;

}

 