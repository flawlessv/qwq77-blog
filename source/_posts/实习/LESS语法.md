---
title: LESS语法
tags:
  - 实习
  - CSS
# categories:
#   - 前端
---

1\. less 简介
-----------

1.  less是CSS的预编译器，可以扩展CSS语言（当然也兼容CSS），可以定义变量、混合、函数等等，让CSS代码更易维护和扩展
2.  less与传统写法相比：

> *   less后缀为" .less "
> *   less中的注释有两种

```
// 这种注释不会编译到CSS文件
/* 这种注释会编译到CSS文件*/
div {
  font-size: 14px;
}

```

3.  less需要编译成css才能使用

> *   使用编译工具，比如 [Koala](https://link.juejin.cn/?target=http%3A%2F%2Fkoala-app.com%2F "http://koala-app.com/") 挺好用的（当然也有很多[在线编译工具](https://link.juejin.cn/?target=https%3A%2F%2Fwww.w3cschool.cn%2Ftools%2Findex%3Fname%3DLESS "https://www.w3cschool.cn/tools/index?name=LESS")）
> *   在项目中使用（比如Vue，需要安装less-loader）
> *   客户端调试（存在跨域问题，不推荐这种方式）
> 
> > *   使用link标签引用less.min.js（[官网下载](https://link.juejin.cn/?target=www.lesscss.cn "www.lesscss.cn")），注意rel="stylesheet/less"
> > *   这种方式不生成css文件，直接在浏览器查看

* * *

2\. 嵌套规则
--------

### 2.1 less的嵌套规则类似HTML的结构，使得CSS代码清晰

```
/*css 写法*/
div {
  font-size: 14px;
}
div p {
 margin: 0 auto;
}

div p a {
  color: red;
}

// less写法
div {
  font-size: 14px;
  p {
    margin: 0 auto;
    a {
      color: red;
    }
  }
}

```

### 2.2 父元素选择符 &

*   表示当前选择器的所有父选择器

```
//css写法
.bgcolor {
  background: #fff;
}
.bgcolor a {
  color: #888888;
}
.bgcolor a:hover {
  color: #ff6600;
}

//less写法
.bgcolor {
  background: #fff; 
  a {
    color: #888888;      
    &:hover {
      color: #ff6600;
    }
  }
}

```

### 2.3 改变选择器的顺序

*   将&放到当前选择器之后，会将当前选择器移到最前面
*   只需记住 “& 代表当前选择器的所有父选择器”

```
ul {
  li {
    .color &{
      background: #fff;
    }
  }
}

//编译结果
.color ul li {
  background: #fff;
}

```

### 2.4 组合使用

*   将生成所有可能的选择器列表

```
.div1, .div2 {
  color: red;
  & & {
    border-top: 1px solid blue;
  }
} 

//编译结果
.div1, .div2 {
  color: red;
}
.div1 .div2,
.div2 .div1,
.div1 .div1,
.div2 .div2 {
  border-top: 1px solid blue;
}

```

* * *

3\. 变量
------

### 3.1 变量的定义和使用

*   定义：@name: value; （@black: #000;）
*   使用场合分3种：

> *   常规使用：@name
> *   作为选择器或属性名：@{name}
> *   作为URL："@{name}"

```
/* 1.常规使用 */
@black: #000000;

div {
  color: @black
}

//编译结果
div {
  color: #000000;
}

/* 2.作用选择器和属性名 */
@selName: container;
@proName: width;

.@{selName} {
  @{proName}: 100px;
}

//编译结果
.container {
  width: 100px;
}

/* 3.作为URL */
@imgUrl: "./images/logo.png"

div {
  background: #FFF url("@{imgUrl}")
}

//编译结果
div {
  background: #FFF url("./images/logo.png")
}

```

### 3.2 注意事项

1.  变量是延迟加载的，可以不预先声明

```
div {
  color: @black
}

@black: #000000;

//编译结果
div {
  color: #000000;
}

```

2.  变量的作用域

> *   less会从当前作用域没找到，将往上查找（类似js）
> *   如果在某级作用域找到多个相同名称的变量，使用最后定义的那个（类似css）

```
@var: 0;
.class {
    @var: 1;
    .brass {
        @var: 2;
        three: @var;
        @var: 3;
    }
    one: @var; //类似js，无法访问.brass内部
}

//编译结果
.class {
    one: 1;
}
.class .brass {
    three: 3;  //使用最后定义的 @var: 3
}

```

* * *

4\. 混合（mixins）
--------------

*   混合：一种将一系列属性从一个规则集引入（“混入”）到另一个规则集的方式
*   混合是非常重要的一个概念，内容也偏多，可以尝试多看几遍！

### 4.1 普通混合

```
//混合
.border {
  border-top: solid 1px black;
  border-bottom: solid 2px black;
}
#menu a {
  color: #eee;
  .border;
}

//编译结果
.border {
  border-top: solid 1px black;
  border-bottom: solid 2px black;
}

#menu a {
  color: #eee;
  border-top: solid 1px black;
  border-bottom: solid 2px black;
}

```

### 4.2 不带参数的混合

*   从上面的代码发现，混合也被编译输出了
*   在混合名字后加上括号，编译后不再输出

```
//加括号但不带参数的混合
.border() {
  border-top: solid 1px black;
  border-bottom: solid 2px black;
}
#menu a {
  color: #eee;
  .border;  //加不加括号都可以
}

//编译结果
#menu a {
  color: #eee;
  border-top: solid 1px black;
  border-bottom: solid 2px black;
}

```

### 4.3 带参数的混合

```
//带参数的混合
.border(@color) {
  border-top: solid 1px @color;
  border-bottom: solid 2px @color;
}
#menu a {
  color: #eee;
  .border(#fff);
}

//编译结果
#menu a {
  color: #eee;
  border-top: solid 1px #ffffff;
  border-bottom: solid 2px #ffffff;
}

```

### 4.4 带参数且有默认值的混合

```
//带参数且有默认值的混合
.border(@color: #fff) {
  border-top: solid 1px @color;
  border-bottom: solid 2px @color;
}
#menu a {
  color: #eee;
  .border;
}

#menu p {
  .border(#000);
}

//编译结果
#menu a {
  color: #eee;
  border-top: solid 1px #ffffff;
  border-bottom: solid 2px #ffffff;
}

#menu p {
  border-top: solid 1px #000000;
  border-bottom: solid 2px #000000;
}

```

### 4.5 带多个参数

*   多个参数时，参数之间可以用分号或逗号分隔
*   **注意逗号分隔的是“各个参数”还是“某个列表类型的参数”**

> *   两个参数，并且每个参数都是逗号分隔的列表：.name(1,2,3; something, ele)
> *   三个参数，并且每个参数都包含一个数字：.name(1,2,3)
> *   使用分号，调用包含一个逗号分割的css列表（一个参数）： .name(1,2,3; )
> *   逗号分割默认值（两个参数）：.name(@param1:red, blue)

```
//less编写
.mixin(@color, @padding: xxx, @margin: 2) {
  color-3: @color;
  padding-3: @padding;
  margin: @margin @margin @margin @margin;
}

.div {
  .mixin(1,2,3; something, ele);  //2个参数
}
.div1 {
  .mixin(1,2,3);                  //3个参数
}
.div2 {
  .mixin(1,2,3; );                //1个参数
}

//编译输出
.div {
  color-3: 1, 2, 3;
  padding-3: something, ele;
  margin: 2 2 2 2;
}
.div1 {
  color-3: 1;
  padding-3: 2;
  margin: 3 3 3 3;
}
.div2 {
  color-3: 1, 2, 3;
  padding-3: xxx;
  margin: 2 2 2 2;
}

```

### 4.6 定义多个相同名称的混合

*   less会根据参数进行调用相应的混合

```
.mixin(@color) {
  color-1: @color;
}
.mixin(@color; @padding: 2) {
  color-2: @color;
  padding-2: @padding;
}
.mixin(@color; @padding: 3; @margin) {
  color-3: @color;
  padding-3: @padding;
  margin: @margin @margin @margin @margin;
}

.some .selector div {
  .mixin(#008000); //第二个mixins也被调用了，因为 @padding 有默认值
}

.some .selector p {
  .mixin(#008000, 5); //只有第二个mixins被调用
}

//编译结果
.some .selector div {
  color-1: #008000;
  color-2: #008000;
  padding-2: 2;
}
.some .selector p {
  color-2: #008000;
  padding-2: 5;
}


```

### 4.7 命名参数

*   引用mixin时可以通过参数名称而不是参数的位置来为mixin提供参数值，任何参数都通过名称来引用，这样就不必按照特定的顺序来使用参数

```
.mixin(@color: black; @margin: 10px; @padding: 20px) {
  color: @color;
  margin: @margin;
  padding: @padding;
}
.class1 {
  .mixin(@margin:20; @color: #33acfe);
}
.class2 {
  .mixin(#efca44; @padding: 40px);
}

//编译输出
.class1 {
  color: #33acfe;
  margin: 20px;
  padding: 20px;
}
.class2 {
  color: #efca44;
  margin: 10px;
  padding: 40px;
}

```

### 4.8 @arguments变量

*   @arguments表示所有可变参数
*   参数的先后顺序就是括号内的顺序 ，在赋值时，值的位置和个数也是一一对应的
*   只有一个值，把值赋给第一个，两个值，赋给第一个和第二个......
*   若想赋给第一个和第三个，必须把第二个参数的默认值写上

```
.border(@x: solid, @c: red) {
  border: 21px @arguments;
}
.div1 {
  .border;
}
.div2 {
  .border(solid, black)
}

//编译输出
.div1 {
  border: 21px solid #ff0000;
}
.div2 {
  border: 21px solid #000000;
}

```

### 4.9 匹配模式

*   自定义一个字符，使用时加上那个字符，就调用相应的规则

```
.border(all, @w: 5px) {
  border-radius: @w;
}
.border(t_l, @w: 5px) {
  border-top-left-radius: @w;
}
.border(b_l, @w: 5px) {
  border-bottom-left-radius: @w;
}
.border(b_r, @w: 5px) {
  border-bottom-right-radius: @w;
}

.border {
  .border(all, 50%);
}
//编译结果
.border {
  border-radius: 50%;
}

```

### 4.10 得到混合中变量的返回值

```
.average(@x, @y) {
  @average((@x + @y)/2);
}

div {
  .average(16px, 50px);
  padding: @average;
}

//编译结果
div {
  padding: 33px;
}
/*
1、将16px 和 50px 赋值给混合 .average进行计算
2、计算结果赋值给变量 @average
3、然后在div中调用@average的值
4、编译后就得到了average的值33px
*/

```

* * *

5\. 运算
------

*   任何数值、颜色值和变量都可以进行运算

### 5.1 数值类运算

*   less会自动推算数值的单位，不必每个值都加上单位
*   运算符之间必须以空格分开，存在优先级问题时注意使用括号

```
.wp {
  width: (450px - 50)*2;
}

//编译输出
.wp {
  width: 900px;
}

```

### 5.2 颜色值运算

*   先将颜色值转换为rgb模式，运算完后再转换为16进制的颜色值并返回
*   注意：取值为0-255，所以计算时不能超过这个区间，超过默认使用0或255
*   注意：不能使用颜色名直接运算

```
.content {
  color: #000000 + 8;
}

//rgb(0,0,0) + 8
//rgb(8,8,8)
//十六进制：#080808

//编译输出
.content {
  color: #080808; 
}

```

* * *

6\. 命名空间
--------

*   有时混合中嵌套了比较多的规则，而我们只需要其中一部分，可使用命名空间获取

### 6.1 使用 ">" 符号

```
//混合集
#bgcolor() {
  background: #fff;
  .a() {
    color: #888;
    &:hover {
      color: #ff6600;
    }
    .b() {
      background: #ff0000;
    }    
  }
}

.bgcolor1 {
  background: #fdfee0;
  #bgcolor>.a;     //只使用.a()
}
.bgcolor2 {
  #bgcolor>.a>.b;  //只使用.b()
}

//编译输出
.bgcolor1 {
  background: #fdfee0;
  color: #888;
}
.bgcolor1:hover {
  color: #ff6600;
}
.bgcolor2 {
  background: #ff0000;
}

```

### 6.2 省略 ">"，换成空格

```
//混合集
#bgcolor() {
  background: #fff;
  .a() {
    color: #888;
    &:hover {
      color: #ff6600;
    }
    .b() {
      background: #ff0000;
    }    
  }
}

.bgcolor1 {
  background: #fdfee0;
  #bgcolor .a;     //只使用.a()
}
.bgcolor2 {
  #bgcolor .a .b;  //只使用.b()
}

//编译输出
.bgcolor1 {
  background: #fdfee0;
  color: #888;
}
.bgcolor1:hover {
  color: #ff6600;
}
.bgcolor2 {
  background: #ff0000;
}

```

* * *

7\. 引入
------

*   引入一个或多个文件，这些文件定义的规则可在当前less文件中使用
*   使用@import

### 7.1 引入less文件

```
//main.less
@wp: 960px;
.color {
  color: #fff;
}

//当前less文件
@import "main"; //可以不加后缀
.content {
  width: @wp;
}

//编译输出
.color {
  color: #fff
}
.content {
  width: 960px;
}

```

### 7.2 引入css文件

*   注意：不能混合css的规则到项目中，编译后原样输出“@import xxx.css”
*   并且引入时不能省略后缀名

```
//main.css
.color {
  color: #ff6600;
}

@import "main.css" ;
.content {
  width: @wp;
  height: @wp;
}

//编译输出
@import "main.css";  //原样输出,但有效，css有这条语句
.content {
  width: 960px;
  height: 960px;
}

```

### 7.3 带参数的引入

*   once：默认，只引入一次
*   reference：使用less文件但不输出，注意对比上面的例子（ 不使用会输出没有加括号的混合）

```
@wp: 960px;
.color {
  color: #fff;
}

//当前less文件
@import (reference) "main";
.content {
  width: @wp;
}

//编译输出
.content {
  width: 960px;
}

```

*   inline：在输出中包含less文件但是不能操作

```
@wp: 960px;
.color {
  color: #fff;
}

//当前less文件
@import (inline) "main"; 
.content {
  width: @wp;
}

//编译输出
@wp: 960px;    //报错，@wp未知
.color {
  color: #fff;
}


```

*   less：将文件作为less文件对象，无论什么文件扩展名

```
//main.css文件
.color {
  color: #ff6600;
}

//当前less
@import (less) "main.css";
  .content {
.color;
}

//编译输出
.color {
  color: #ff6600;
}
.content {
  color: #ff6600;
}

```

*   css：将文件作为css文件对象，无论什么文件扩展名

```
//当前less文件
@import (css) "main.less";
.content {
  color: red;
}

//编译输出
@import "main.less";
.content {
  color: red;
}

```

*   multiple：允许引入多次相同文件名的文件

```
//当前less
@import (multiple) "main.less";
@import (multiple) "main.less";
@import (multiple) "main.less";
.content {
  width: @wp;
}

//编译输出
.color {
  color: #fff;
}
.color {
  color: #fff;
}
.color {
  color: #fff;
}
.content {
  width: 960px;
}

```

* * *

8\. !important
--------------

*   提升权重优先级为最高（尽量避免使用）
*   在调用的混合集后面追加 !important 关键字，混合集中所有属性都继承 !important

```
.foo(@bg: #fdfdfd, @color: #900) {
  background: @bg;
  color: @color;
}

.important {
  .foo() !important
}

//编译输出
.important {
  background: #fdfdfd !important;
  color: #990000 !important;
}

```

* * *

9\. 条件表达式
---------

### 9.1 带条件的混合

*   比较运算符：>, >=, =, =<, <
*   格式：when() { }

```
// lightness() 是检测亮度的函数，用%度量
.mixin(@a) when(lightness(@a) >= 50% ) {
  background-color: black;
}
.mixin(@a) when(lightness(@a) < 50% ) {
  background-color: white;
}

.mixin(@a) {
  color: @a;
}
.class1 {
  .mixin(#ddd);
}
.class2 {
  .mixin(#555);
}

//编译输出
.class1 {
  background-color: black;
  color: #dddddd;
}
.class2 {
  background-color: white;
  color: #555555;
}

```

### 9.2 类型检测函数

*   检测值的类型

> *   iscolor
> *   isnumber
> *   isstring
> *   iskeyword
> *   isurl

```
.mixin(@a: #fff; @b: 0) when(isnumber(@b)) {
  color: @a;
  font-size: @b;
}
.mixin(@a; @b: black) when(iscolor(@b)) {
  font-size: @a;
  color: @b;
}

```

### 9.3 单位检测函数

*   检测一个值除了数字是否是一个特定的单位

> *   ispixel
> *   ispercentage
> *   isem
> *   isunit

```
.mixin(@a) when(ispixel(@a)) {
  width: @a;
}
.mixin(@a) when(ispercentage(@a)) {
  width: @a;
}

.class1 {
  .mixin(960px);
}
.class2 {
  .mixin(95%);
}

//编译输出
.class1 {
  width: 960px;
}
.class2 {
  width: 95%;
}

```

* * *

10\. 循环
-------

*   混合可以调用自身，当一个混合递归调用自身就构成循环结构

```
.loop(@counter) when(@counter > 0) {
  .h@{counter} {
    padding: (10px*@counter);
  }
  .loop((@counter - 1)); //递归调用自身
}
div{
  .loop(5);
}

//编译输出
div .h5 {
  padding: 50px;
}
div .h4 {
  padding: 40px;
}
div .h3 {
  padding: 30px;
}
div .h2 {
  padding: 20px;
}
div .h1 {
  padding: 10px;
}

```

* * *

11\. 合并属性
---------

*   将多条规则合并为一条

### 11.1 方式一

*   在需要合并的属性的冒号之前加上 **“+”**，合并后用逗号分隔

```
.mixin() {
  box-shadow+: inset 0 0 10px #555;
}
.myclass {
  .mixin;
  box-shadow+: 0 0 20px black;
}

//编译输出
.myclass {
  box-shadow: inset 0 0 10px #555, 0 0 20px black; //逗号分隔两个属性值

```

### 11.2 方式二

*   在需要合并的属性的冒号之前加上 “+\_”，合并用空格分隔

```
.mixin() {
  background+_: #f66;
  background+_: url("/sss.jpg") 
}

.class {
  .mixin;
}

//编译输出
.class {
  background: #f66 url("/sss.jpg"); //空格分隔
} 

```

### 11.3 两种方式结合

```
.mixin() {
  background+_: #f66;
  background+: url("/sss.jpg");
  background+_: no-repeat;
  background+: center;
}
.class {
  .mixin;
}

//编译输出
.class {
  background: #f66, url("/sss.jpg")  no-repeat, center;
}

```

* * *

12\. 函数库
--------

*   less中封装了非常多函数库，例如颜色定义、颜色操作、颜色混合、字符串处理等等
    
*   例如color()：用于解析颜色，将代表颜色的字符串转换为颜色值
    

```
body {
  color: color("#f60");
  background: color("red");
}

//编译输出
body {
  color: #ff6600;
  background: #ff0000;
}

```

*   例如convert()：将数字从一种类型（单位）转换为另一种类型

> *   长度单位：m, cm, mm, in, pt, px, pc
> *   时间单位：s, ms
> *   角度单位：rad(弧度), deg(度), grad(梯度), tum(圆)

```
body {
  width: convert(20cm, px);
}

//编译输出
body {
  width: 755.90551181px;
}

```