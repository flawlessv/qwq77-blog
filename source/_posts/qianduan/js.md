---
title: JavaScript笔记
tags:
  - JavaScript

---
**本文作者**[秋一](https://godv.cc/readme/)

### 初识JavaScirpt

- JavaScript 是世界上最流行的语言之一，是一种运行在客户端的脚本语言 （Script 是脚本的意思）
- 脚本语言：不需要编译，运行过程中由 js 解释器( js 引擎）逐行来进行解释并执行
- 现在也可以基于 Node.js 技术进行服务器端编程

### 浏览器执行JS简介

浏览器分成两部分：渲染引擎和 JS 引擎

- 渲染引擎：用来解析HTML与CSS，俗称内核，比如 chrome 浏览器的 blink ，老版本的 webkit
- JS 引擎：也称为 JS 解释器。 用来读取网页中的JavaScript代码，对其处理后运行，比如 chrome 浏览器的 V8

浏览器本身并不会执行JS代码，而是通过内置 JavaScript 引擎(解释器) 来执行 JS 代码 。JS 引擎执行代码时逐行解释每一句源码（转换为机器语言），然后由计算机去执行，所以 JavaScript 语言归为脚本语言，会逐行解释执行。

### JS的组成

JavaScript 包括 ECMAScript、DOM、BOM

![](https://img-blog.csdnimg.cn/a9331f588aa54d43b22ae207249f0e1f.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L0F1Z2Vuc3Rlcm5fUVhM,size_16,color_FFFFFF,t_70#pic_center)

### DOM文档对象模型

**文档对象模型**（Document Object Model，简称DOM），是W3C组织推荐的处理可扩展标记语言的标准编程接口。通过 DOM 提供的接口可以对页面上的各种元素进行操作（大小、位置、颜色等）。

### BOM浏览器对象模型

**BOM** (Browser Object Model，简称BOM) 是指浏览器对象模型，它提供了独立于内容的、可以与浏览器窗口进行互动的对象结构。通过BOM可以操作浏览器窗口，比如弹出框、控制浏览器跳转、获取分辨率等。

### 输入输出语句

| 方法              | 说明                           | 归属   |
| ----------------- | ------------------------------ | ------ |
| alert(msg);       | 浏览器弹出警示框               | 浏览器 |
| console.log(msg); | 浏览器控制台打印输出信息       | 浏览器 |
| prompt(info);     | 浏览看弹出输入框，用户可以输入 | 浏览器 |

### 声明变量特殊情况

| 情况                       | 说明                   | 结果      |
| -------------------------- | ---------------------- | --------- |
| var age; console.log(age); | 只声明，不赋值         | undefined |
| console.log(age)           | 不声明 不赋值 直接使用 | 报错      |
| age = 10;console.log(age); | 不声明 只赋值          | 10        |

### 变量的命名规范

由字母(A-Z,a-z)，数字(0-9)，下划线(_)，美元符号($)组成，如:usrAge,num01,__name

严格区分大小写。 var app; 和 var App; 是两个变量

不能以数字开头。

不能是关键字，保留字。例如：var,for,while

遵循驼峰命名法。首字母小写，后面单词的首字母需要大写。myFirstName

推荐翻译网站：有道 爱词霸

### 数据类型

JavaScript **是一种弱类型或者说动态语言。**这意味着不用提前声明变量的类型，在程序运行过程中，类型会被自动确定。

var age = 10; 			 //这是一个数字型
var areYouOk = '使得';	//这是一个字符串

在代码运行时，变量的数据类型是由 JS引擎 根据 = 右边变量值的数据类型来判断 的，运行完毕之后， 变量就确定了数据类型。  
JavaScript 拥有动态类型，同时也意味着相同的变量可用作不同的类型

var x = 6;		//x为数字
var x = "Bill";	//x为字符串

JS 把数据类型分为两类：

基本数据类型(Number,String,Boolean,Undefined,Null)
复杂数据类型(Object)
#### 基本数据类型

| 简单数据类型 | 说明                                            | 默认值                |
| ------------ | ----------------------------------------------- | --------------------- |
| Number       | 数字型，包含整型值和浮点型值，如21，0.21        | 0                     |
| Boolean      | 布尔值类型，如true，false ，等价于1和0          | false                 |
| Undefined    | var a; 声明了变量a但是没有赋值，此时a=undefined | undefined（未定义的） |
| string       | 字符串类型，如“张三”                            | “”                    |
| Null         | var a = null;声明了变量a为空值                  | null                  |

#### 数字型Number

JavaScript 数字类型既可以用来保存整数值，也可以保存小数(浮点数）。

最常见的进制有二进制、八进制、十进制、十六进制。

**在JS中八进制前面加0，十六进制前面加 0x**

##### 数字型范围

JS中数值的最大值：`Number.MAX_VALUE`

JS中数值的最小值：`Number.MIN_VALUE`

##### 数字型的三个特殊值

- Infinity ，代表无穷大，大于任何数值
- -Infinity ，代表无穷小，小于任何数值
- Nan ，Not a Number，代表一个非数值

##### isNaN

这个方法用来判断非数字，并且返回一个值，如果是数字返回的是false，如果不是数字返回的是true

```js
var userAge = 21;
var isOk = isNan(userAge);
console.log(isOk);		//false,21不是一个非数字
```

#### 字符串型String

因为 HTML 标签里面的属性使用的是双引号，JS 这里我们更推荐**使用单引号**。

#### ①字符串引号嵌套

JS可以用 **单引号嵌套双引号**，或者用 **双引号嵌套单引号**（**外双内单，外单内双**）

#### ②字符串转义符

类似HTML里面的特殊字符，字符串中也有特殊字符，我们称之为转义符。

转义符都是 \ 开头的，常用的转义符及其说明如下：

| 转义符 | 解释说明             |
| ------ | -------------------- |
| \n     | 换行符，n是newline   |
| \ \    | 斜杠\                |
| \ ’    | ’ 单引号             |
| \ ‘’   | ‘’ 双引号            |
| \ t    | tab 缩进             |
| \ b    | 空格，b是blank的意思 |

#### 字符串的拼接

- 多个字符串之间可以使用 + 进行拼接，其拼接方式为 **字符串 + 任何类型 = 拼接之后的新字符串**
- 拼接前会把与字符串相加的任何类型转成字符串，再拼接成一个新的字符串

**注意**：字符串 + 任何类型 =拼接之后的新字符串

如果变量两侧都有字符串拼接，口诀==🌏“引引加加 ”，删掉数字🌏==变量写加中间

#### 布尔型Boolean

- 布尔类型有两个值：true 和 false ，其中 true 表示真（对），而 false 表示假（错）。
- 布尔型和数字型相加的时候， true 的值为 1 ，false 的值为 0。

#### undefined未定义

一个**声明后没有被赋值**的变量会有一个默认值 undefined ( 如果进行相连或者相加时，注意结果）

```js
// 如果一个变量声明未赋值，就是undefined 未定义数据类型
var str;
console.log(str);				//undefined
var variable = undefined;
console.log(variable + 'Pink'); //undefinedPink
console.log(variable + 18); //NaN 
```

1.undefined 和 字符串 相加，会拼接字符串

2.undefined 和 数字相加，最后结果是**NaN**

#### 空值null

一个声明变量给 null 值，里面存的值为空

```js
var space = null;
console.log(space + 'pink'); //nullpink
console.llog(space + 1); // 1 
```

#### typeof

- typeof 可用来获取检测变量的数据类型

```js
var num = 18;
console.log(typeof num) // 结果 number  
```

### 数据类型转换

使用表单、prompt 获取过来的数据默认是字符串类型的，此时就不能直接简单的进行加法运算，而需要转换变量的数据类型。通俗来说，**就是把一种数据类型的变量转换成另外一种数据类型**。

我们通常会实现3种方式的转换：

- 转换为字符串类型
- 转换为数字型
- 转换为布尔型

### ①转换为字符串型

| 方式               | 说明                         | 案例                                 |
| ------------------ | ---------------------------- | ------------------------------------ |
| toString()         | 转成字符串                   | var num = 1; alert(num.toString());  |
| String()强制转换   | 转成字符串                   | var num = 1; alert(String(num));     |
| **加号拼接字符串** | 和字符串拼接的结果都是字符串 | var num =1; alert(num+“我是字符串”); |

- toString() 和 String() 使用方式不一样
- 三种转换方式，我们更喜欢用第三种加号拼接字符串转换方式，这一方式也称为隐式转换

### ②转换为数字型

| 方式                       | 说明                         | 案例                |
| -------------------------- | ---------------------------- | ------------------- |
| **parselnt(string)函数**   | 将string类型转成整数数值型   | parselnt(‘78’)      |
| **parseFloat(string)函数** | 将string类型转成浮点数数值型 | parseFloat(‘78.21’) |
| Number()强制转换函数       | 将string类型转换为数值型     | Number(‘12’)        |
| js 隐式转换(- * /)         | 利用算术运算隐式转换为数值型 | ‘12’-0              |

### ③转换为布尔型

| 方法          | 说明               | 案例             |
| ------------- | ------------------ | ---------------- |
| Boolean()函数 | 其他类型转成布尔值 | Boolean(‘true’); |

- 代表空，否定的值会被转换为false，如 ’ ’ , 0, NaN , null , undefined
- 其余的值都会被被转换为true

== 默认转换数据类型会把字符串型的数据转换为数字型

### 运算符

#### 浮点数的精度问题

浮点数值的最高精度是17位小数，但在进行算数计算时其精确度远远不如整数

#### 递增和递减运算符

递增（++）

递减（- -）

放在变量前面时，我们称为**前置递增(递减)运算符**

放在变量后面时，我们称为**后置递增(递减)运算符**

**注意**：递增和递减运算符必须和变量配合使用。

#### ①前置递增运算符🔥

++num num = num + 1

使用口诀:**先自加，后返回值**

```js
var num = 10;
alert (++num + 10); // 21
12
```

先自加 10+1=11，返回11，此时num=11

#### ②后置递增运算符🔥

num ++ num = num +1

使用口诀:**先返回原值，后自加**

```js
var num = 10;
alert(10 + num++); // 20
```

#### ③小结🔥

- 前置递增和后置递增运算符可以简化代码的编写，让变量的值 + 1 比以前写法更简单
- 单独使用时，运行结果相同，与其他代码联用时，执行结果会不同
- 开发时，大多使用后置递增/减，并且代码独占一行

#### 比较(关系)运算符

比较运算符是**两个数据进行比较时所使用的运算符**，比较运算后，会**返回一个布尔值**(true / false)作为比较运算的结果。

| 运算符名称 | 说明                        | 案例        | 结果  |
| ---------- | --------------------------- | ----------- | ----- |
| <          | 小于号                      | 1 < 2       | true  |
| >          | 大于号                      | 1 > 2       | false |
| >=         | 大于等于号(大于或者等于)    | 2 >= 2      | true  |
| <=         | 小于等于号(小于或者等于)    | 3 <= 2      | false |
| ==         | 判等号(会转型)              | 37 == 37    | true  |
| !=         | 不等号                      | 37 != 37    | false |
| === !==    | 全等 要求值和数据类型都一致 | 37 === ‘37’ | false |

#### 逻辑运算符

辑运算符是用来进行布尔值运算的运算符，其返回值也是布尔值

| 逻辑运算符 | 说明                   | 案例            |
| ---------- | ---------------------- | --------------- |
| &&         | “逻辑与”，简称"与" and | true && false   |
| \|\|       | “逻辑或”，简称"或" or  | true \|\| false |
| ！         | “逻辑非”，简称"非" not | ！true          |

#### 短路运算(逻辑中断)

短路运算的原理：当有多个表达式（值）时,左边的表达式值可以确定结果时,就不再继续运算右边的表达式的值

##### ①逻辑与🔥

- 语法：表达式1 && 表达式2
- 如果第一个表达式的值为真，则返回表达式2
- 如果第一个表达式的值为假，则返回表达式1

##### ②逻辑或

- 语法：表达式1 || 表达式2
- 如果第一个表达式的值为真，则返回表达式1
- 如果第一个表达式的值为假，则返回表达式2

#### 赋值运算符

概念：用来把数据赋值给变量的运算符。

| 赋值运算符 | 说明                 | 案例                        |
| ---------- | -------------------- | --------------------------- |
| =          | 直接赋值             | var usrName = ‘我是值’      |
| += ，-=    | 加，减一个数后再赋值 | var age = 10； age+=5；//15 |
| *=，/=，%= | 成，除，取模后再赋值 | var age = 2; age*=5; //10   |

#### 运算符优先级

| 优先级 | 运算符     | 顺序                          |
| ------ | ---------- | ----------------------------- |
| 1      | 小括号     | ()                            |
| 2      | 一元运算符 | ++ – ！                       |
| 3      | 算数运算符 | **先 \* / 后 + -**            |
| 4      | 关系运算符 | **>, >= , < , <=**,           |
| 5      | 相等运算符 | ，！=，=，！==                |
| 6      | 逻辑运算符 | **先 && 后 \|\|（先与后或）** |
| 7      | 赋值运算符 | =                             |
| 8      | 逗号运算符 | ，                            |

1.一元运算符里面的**逻辑非**优先级很高

2.**逻辑与** 比 **逻辑或** 优先级高

### 三元表达式

- 语法结构 : 表达式1 ? 表达式2 : 表达式3
- 执行思路

如果表达式1为true，则返回表达式2的值,如果表达式1为false，则返回表达式3的值

### 断点调试

浏览器中按 F12–> sources -->找到需要调试的文件–>在程序的某一行设置断点(在行数点一下)

刷新浏览器

Watch: 监视，通过watch可以监视变量的值的变化，非常的常用

F11: 程序单步执行，让程序一行一行的执行，这个时候，观察watch中变量的值的变化

### continue 关键字

continue 关键字用于**立即跳出本次循环，继续下一次循环**（本次循环体中 continue 之后的代码就会少执行一次）。

### break关键字

break 关键字用于**立即跳出整个循环**

### 数组

#### 创建数组

JavaScript 中创建数组有两种方式：

- 利用 new 创建数组
- 利用数组字面量创建数组

#### ①利用 new 创建数组🔥

```js
var 数组名 = new Array();
var arr = new Array(); //创建一个新的空数组
```

注意 `Array()`，A要大写

#### ②利用数组字面量创建数组

```js
// 1.利用数组字面量方式创建空的数组 
var 数组名 =[];
// 2.使用数组字面量方式创建带初始值的数组
var 数组名 =['小白','小黑','小黄','瑞奇'];
// 3.数组中可以存放任意类型的数据，例如字符串，数字，布尔值等
var arrStus =['小白'，12,true,28.9];
```

- 数组的字面量是方括号 `[]`
- 声明数组并赋值称为数组的初始化
- 这种字面量方式也是我们以后最多使用的方式

#### 数组中新增元素

#### ①通过修改 length 长度新增数组元素

- 可以通过修改 length 长度来实现数组扩容的目的
- length 属性是可读写的

```js
var arr = ['red', 'green', 'blue', 'pink'];
arr.length = 7;
console.log(arr);
console.log(arr[4]);
console.log(arr[5]);
console.log(arr[6]);
```

#### ②通过修改数组索引新增数组元素

- 可以通过修改数组索引的方式追加数组元素
- 不能直接给数组名赋值，否则会覆盖掉以前的数据
- 这种方式也是我们最常用的一种方式

```js
var arr = ['red', 'green', 'blue', 'pink'];
arr[4] = 'hotpink';
console.log(arr);
```

### 函数

函数：就是封装了一段**可被重复调用执行的代码块**。通过此代码块可以实现大量代码的重复使用。

#### 函数的使用

函数在使用时分为两步：**声明函数**和**调用函数**

#### ①声明函数🔥

```js
//声明函数
function 函数名(){
     //函数体代码
}
```

- function 是声明函数的关键字,**必须小写**
- 由于函数一般是为了实现某个功能才定义的， 所以通常我们将函数名命名为动词，比如 getSum

#### ②调用函数

```js
//调用函数
函数名(); //通过调用函数名来执行函数体代码
```

- 调用的时候**千万不要忘记添加小括号**
- 口诀：函数不调用，自己不执行

**注意**：声明函数本身并不会执行代码，只有调用函数时才会执行函数体代码。

#### 函数的参数

#### 形参和实参

**在声明函数时**，可以在函数名称后面的小括号中添加一些参数，这些参数被称为**形参**，而在**调用该函数**时，同样也需要传递相应的参数，这些参数被称为**实参**。

| 参数     | 说明                                                         |
| -------- | ------------------------------------------------------------ |
| **形参** | **形**式上的**参**数 **函数定义**的时候 传递的参数 当前并不知道是什么 |
| **实参** | **实**际上的**参**数 **函数调用**的时候 传递的参数 实参是传递给形参的 |

**参数的作用** : 在**函数内部**某些值不能固定，我们可以通过参数在**调用函数时传递不同的值**进去

```javascript
// 带参数的函数声明
function 函数名(形参1, 形参2 , 形参3...) { // 可以定义任意多的参数，用逗号分隔
  // 函数体
}


// 带参数的函数调用
函数名(实参1, 实参2, 实参3...); 
```

#### 形参和实参个数不匹配

| 参数个数             | 说明                               |
| -------------------- | ---------------------------------- |
| 实参个数等于形参个数 | 输出正确结果                       |
| 实参个数多于形参个数 | 只取到形参的个数                   |
| 实参个数小于形参个数 | 多的形参定义为undefined，结果为NaN |

**注意：在JavaScript中，形参的默认值是undefined**

#### 函数的返回值

##### return语句

有的时候，我们会希望函数将值返回给调用者，此时通过使用 return 语句就可以实现。

return 语句的语法格式如下：

```js
/ 声明函数
function 函数名（）{
    ...
    return  需要返回的值;
}
// 调用函数
函数名();    // 此时调用函数就可以得到函数体内return 后面的值
```

- 在使用 return 语句时，函数会停止执行，并返回指定的值
- 如果函数没有 return ，返回的值是 undefined

#### return 终止函数

return 语句之后的代码不被执行

#### return 的返回值

return **只能返回一个值**。如果用逗号隔开多个值，**以最后一个为准**

#### arguments的使用

当我们不确定有多少个参数传递的时候，可以用 arguments 来获取。在 JavaScript 中，arguments 实际上它是当前函数的一个内置对象。所有函数都内置了一个 arguments 对象，arguments 对象中存储了传递的所有实参。

- arguments存放的是传递过来的实参
- 
- arguments展示形式是一个伪数组，因此可以进行遍历。伪数组具有以下特点

 ①：具有 length 属性

 ②：按索引方式储存数据

 ③：不具有数组的 push , pop 等方法

#### 函数调用另外一个函数

因为每个函数都是独立的代码块，用于完成特殊任务，因此经常会用到函数相互调用的情况。具体演示在下面的函数练习中会有。

#### 函数的两种声明方式

##### 自定义函数方式(命名函数)

利用函数关键字 function 自定义函数方式。

```js
// 声明定义方式
function fn() {...}

// 调用  
fn();  
```

1. **因为有名字，所以也被称为命名函数**
2. **调用函数的代码既可以放到声明函数的前面，也可以放在声明函数的后面**

##### 函数表达式方式(匿名函数)

利用函数表达式方式的写法如下：

```js
// 这是函数表达式写法，匿名函数后面跟分号结束
var fn = function(){...};

// 调用的方式，函数调用必须写到函数体下面
fn();
```

- 因为函数没有名字，所以也称为**匿名函数**
- 这个fn 里面存储的是一个函数
- **函数调用的代码必须写到函数体后面**

### 作用域

通常来说，一段程序代码中所用到的名字并不总是有效和可用的，而限定这个名字的**可用性的代码范围**就是这个名字的**作用域**。作用域的使用提高了程序逻辑的局部性，增强了程序的可靠性，减少了名字冲突。

JavaScript (ES6前) 中的作用域有两种：

- 全局作用域
- 局部作用域(函数作用域)

#### 全局作用域

作用于所有代码执行的环境(整个 script 标签内部)或者一个独立的 js 文件

#### 局部（函数）作用域

作用于函数内的代码环境，就是局部作用域。 因为跟函数有关系，所以也称为函数作用域

#### JS 没有块级作用域（es6之前）

- 块作用域由 `{}` 包括
- 在其他编程语言中（如 java、c#等），在 if 语句、循环语句中创建的变量，仅仅只能在本 if 语句、本循环语句中使用

#### 变量的作用域

在JavaScript中，根据作用域的不同，变量可以分为两种：

- 全局变量
- 局部变量

#### 全局变量

在全局作用域下声明的变量叫做全局变量（**在函数外部定义的变量**）

- 全局变量在代码的任何位置都可以使用
- 在全局作用域下 var 声明的变量 是全局变量
- 特殊情况下，在函数内不使用 var 声明的变量也是全局变量（不建议使用）

#### 局部变量

在局部作用域下声明的变量叫做局部变量（**在函数内部定义的变量**）

- 局部变量只能在该函数内部使用
- 在函数内部 var 声明的变量是局部变量
- 函数的**形参**实际上就是**局部变量**

#### 区别

- 全局变量：在任何一个地方都可以使用，只有在浏览器关闭时才会被销毁，因此比较占内存
- 局部变量：只在函数内部使用，当其所在的代码块被执行时，会被初始化；当代码块运行结束后，就会被销毁，因此更节省内存空间

### 作用域链

1. 只要是代码，就至少有一个作用域
2. 写在函数内部的叫局部作用域
3. 如果函数中还有函数，那么在这个作用域中就又可以诞生一个作用域
4. 根据在内部函数可以访问外部函数变量的这种机制，用链式查找决定哪些数据能被内部函数访问，就称作作用域链

```js
// 作用域链: 内部函数访问外部函数的变量，采取的是链式查找的方式来决定取哪个值，这种结构我们称为作用域链表
var num = 10;
funtion fn() { //外部函数
    var num = 20;
    function fun() { //内部函数
        console.log(num);  // 20 ,一级一级访问
    }

}
```

作用域链：采取**就近原则**的方式来查找变量最终的值。

### 预解析

JavaScript 代码是由浏览器中的 JavaScript 解析器来执行的。JavaScript 解析器在运行 JavaScript 代码的时候分为两步：预解析和代码执行。

- 预解析：js引擎会把js里面所有的 var 还有 function 提升到当前作用域的最前面
- 
- 代码执行：从上到下执行JS语句
预解析只会发生在通过 var 定义的变量和 function 上。学习预解析能够让我们知道**为什么在变量声明之前访问变量的值是 undefined**，**为什么在函数声明之前就可以调用函数。**

#### 变量预解析(变量提升)

变量预解析也叫做变量提升、函数提升

变量提升: 变量的声明会被提升到**当前作用域**的最上面，变量的赋值不会提升

#### 函数预解析(函数提升)

函数提升： 函数的声明会被提升到**当前作用域**的最上面，但是不会调用函数。

#### 解决函数表达式声明调用问题

对于函数表达式声明调用需要记住：**函数表达式调用必须写在函数声明的下面**

### 对象

在 JavaScript 中，对象是一组无序的相关属性和方法的集合，所有的事物都是对象，例如字符串、数值、数组、函数等。

对象是由属性和方法组成的：

- 属性：事物的**特征，\**在对象中用\**属性**来表示（常用名词）
- 方法：事物的**行为，\**在对象中用\**方法**来表示（常用动词）

#### 创建对象

在 JavaScript 中，现阶段我们可以采用三种方式创建对象（object）：

- 利用字面量创建对象
- 利用 new Object创建对象
- 利用构造函数创建对象

##### ①利用字面量创建对象

对象字面量：就是花括号 `{ }` 里面包含了表达这个具体事物（对象）的属性和方法

`{ }` 里面采取键值对的形式表示

- 键：相当于属性名
- 值：相当于属性值，可以是任意类型的值（数字类型、字符串类型、布尔类型，函数类型等）

```js
var star = {
    name : 'pink',
    age : 18,
    sex : '男',
    sayHi : function(){
        alert('大家好啊~');
    }
};
// 多个属性或者方法中间用逗号隔开
// 方法冒号后面跟的是一个匿名函数
```

##### 对象的调用

- 对象里面的属性调用 : 对象.属性名 ，这个小点 . 就理解为“ **的** ”
- 对象里面属性的另一种调用方式 : 对象[‘属性名’]，注意方括号里面的属性必须**加引号**，我们后面会用
- 对象里面的方法调用：对象.方法名() ，注意这个方法名字后面**一定加括号**

```js
console.log(star.name)     // 调用名字属性
console.log(star['name'])  // 调用名字属性
star.sayHi();              // 调用 sayHi 方法,注意，一定不要忘记带后面的括号
```

#### 变量、属性、函数、方法总结

- 变量：单独声明赋值，单独存在
- 属性：对象里面的变量称为属性，不需要声明，用来描述该对象的特征
- 函数：单独存在的，通过==“函数名()”==的方式就可以调用
- 方法：对象里面的函数称为方法，方法不需要声明，使用==“对象.方法名()”==的方式就可以调用，方法用来描述该对象的行为和功能。

##### ②利用 new Object 创建对象

跟之前的 `new Array()` 原理一致：`var 对象名 = new Object();`

使用的格式：对象.属性 = 值

```js
var obj = new Object(); //创建了一个空的对象
obj.name = '张三丰';
obj.age = 18;
obj.sex = '男';
obj.sayHi = function() {
    console.log('hi~');
}
//1.我们是利用等号赋值的方法添加对象
//2.每个属性和方法之间用分号结束
console.log(obj.uname);
console.log(obj['sex']);
obj.sayHi();
```

##### ③利用构造函数创建对象

构造函数 ：是一种特殊的函数，主要用来初始化对象，即为对象成员变量赋初始值，它总与 new 运算符一起使用。我们可以把对象中一些公共的属性和方法抽取出来，然后封装到这个函数里面。

在 js 中，使用构造函数要时要注意以下两点：

构造函数用于创建某一类对象，其首字母要大写
构造函数要和 new 一起使用才有意义

```js
//构造函数的语法格式
function 构造函数名() {
    this.属性 = 值;
    this.方法 = function() {}
}
new 构造函数名();
```

```js
//1. 构造函数名字首字母要大写
//2. 构造函数不需要return就可以返回结果
//3. 调用构造函数必须使用 new
//4. 我们只要new Star() 调用函数就创建了一个对象
//5. 我们的属性和方法前面必须加this
function Star(uname,age,sex) {
    this.name = uname;
    this.age = age;
    this.sex = sex;
    this.sing = function(sang){
        console.log(sang);
    }
}
var ldh = new Star('刘德华',18,'男');
console.log(typeof ldh) // object对象，调用函数返回的是对象

console.log(ldh.name);
console.log(ldh['sex']);
ldh.sing('冰雨');
//把冰雨传给了sang

var zxy = new Star('张学友',19,'男');
```

- 构造函数名字首字母要大写
- 函数内的属性和方法前面需要添加 this ，表示当前对象的属性和方法。
- 构造函数中不需要 return 返回结果。
- 当我们创建对象的时候，必须用 new 来调用构造函数。

#### 构造函数和对象

- 构造函数，如 Stars()，抽象了对象的公共部分，封装到了函数里面，它泛指某一大类（class）
- 创建对象，如 new Stars()，特指某一个，通过 new 关键字创建对象的过程我们也称为对象实例化

#### new关键字

new 在执行时会做四件事:

1. 在内存中创建一个新的空对象。
2. 让 this 指向这个新的对象。
3. 执行构造函数里面的代码，给这个新对象添加属性和方法
4. 返回这个新对象（所以构造函数里面不需要return）

#### 遍历对象的属性

`for...in` 语句用于对数组或者对象的属性进行循环操作

语法如下

```语法中的变量是自定义的，它需要符合命名规范，通常我们会将这个变量写为 k 或者 key。
for(变量 in 对象名字){
    // 在此执行代码
}
```

语法中的变量是自定义的，它需要符合命名规范，通常我们会将这个变量写为 k 或者 key。

```js
for(var k in obj) {
    console.log(k);		//这里的 k 是属性名
    console.log(obj[k]);//这里的 obj[k] 是属性值
}
```

```js
var obj = {
    name: '秦sir',
    age: 18,
    sex: '男',
    fn:function() {};
};
console.log(obj.name);
console.log(obj.age);
console.log(obj.sex);

//for in 遍历我们的对象
//for (变量 in 对象){}
//我们使用for in 里面的变量 我们喜欢写k 或者key
for(var k in obj){
    console.log(k); // k 变量 输出得到的是属性名
    console.log(obj[k]); // obj[k] 得到的是属性值
}
```

### 内置对象

- JavaScript 中的对象分为3种：自定义对象 、内置对象、 浏览器对象
- 内置对象就是指 JS 语言自带的一些对象，这些对象供开发者使用，并提供了一些常用的或是最基本而必要的功能
- JavaScript 提供了多个内置对象：Math、 Date 、Array、String等

### 查文档

学习一个内置对象的使用，只要学会其常用成员的使用即可，我们可以通过查文档学习，可以通过MDN/W3C来查询

MDN: https://developer.mozilla.org/zh-CN/

#### 如何学习对象中的方法

1. 查阅该方法的功能
2. 查看里面参数的意义和类型
3. 查看返回值的意义和类型
4. 通过 demo 进行测试

### Math对象

Math 对象不是构造函数，它具有数学常数和函数的属性和方法。跟数学相关的运算（求绝对值，取整、最大值等）可以使用 Math 中的成员。

```js
// Math数学对象，不是一个构造函数，所以我们不需要new 来调用，而是直接使用里面的属性和方法即可
Math.PI		 			// 圆周率
Math.floor() 	 		// 向下取整
Math.ceil()             // 向上取整
Math.round()            // 四舍五入版 就近取整   注意 -3.5   结果是  -3 
Math.abs()		 		// 绝对值
Math.max()/Math.min()	// 求最大和最小值 
```

**注意**：上面的方法必须带括号

`Math.round()` : 四舍五入，其他数字都是四舍五入，但是5特殊，它往大了取

#### 随机数方法random()

- random() 方法可以随机返回一个小数，其取值范围是 [0，1)，左闭右开 0 <= x < 1
- 得到一个两数之间的随机整数，包括第一个数，不包括第二个数

```js
// 得到两个数之间的随机整数，并且包含这两个整数
function getRandom(min,max) {
    return Math.floor(Math.random() * (max - min + 1)) + min;
}
console.log(getRandom(1,10));
```

### Data()日期对象

- Date 对象和 Math 对象不一样，他是一个构造函数，所以我们需要实例化后才能使用
- Date 实例用来处理日期和时间

#### Date()方法的使用

##### 获取当前时间必须实例化

```js
var now = new Date();
console.log(now);
```

#### Date()构造函数的参数

如果括号里面有时间，就返回参数里面的时间。例如日期格式字符串为 `‘2019-5-1’`，可以写成`new Date('2019-5-1')` 或者 `new Date('2019/5/1')`

- 如果Date()不写参数，就返回当前时间
- 如果Date()里面写参数，就返回括号里面输入的时间

```js
// 1.如果没有参数，返回当前系统的当前时间
var now = new Date();
console.log(now);
// 2.参数常用的写法 数字型 2019,10,1  字符串型 '2019-10-1 8:8:8' 时分秒
// 如果Date()里面写参数，就返回括号里面输入的时间 
var data = new Date(2019,10,1);
console.log(data);  // 返回的是11月不是10月
var data2 = new Date('2019-10-1 8:8:8');
console.log(data2);
```

#### 日期格式化

| 方法名        | 说明                     | 代码               |
| ------------- | ------------------------ | ------------------ |
| getFullYear() | 获取当年                 | dObj.getFullYear() |
| getMonth()    | 获取当月(0-11)           | dObj.getMonth()    |
| getDate()     | 获取当天日期             | dObj.getDate()     |
| getDay()      | 获取星期几(周日0到周六6) | dObj.getDay()      |
| getHours()    | 获取当前小时             | dObj.getHours()    |
| getMinutes()  | 获取当前小时             | dObj.getMinutes()  |
| getSeconds()  | 获取当前秒钟             | dObj.gerSeconds()  |

#### 获取日期的总的毫秒形式

- `date.valueOf()` ：得到现在时间距离1970.1.1总的毫秒数
- `date.getTime()` ：得到现在时间距离1970.1.1总的毫秒数

```js
// 获取Date总的毫秒数 不是当前时间的毫秒数 而是距离1970年1月1号过了多少毫秒数

// 实例化Date对象
var date = new Date();

// 1 .通过 valueOf()  getTime() 用于获取对象的原始值
console.log(date.valueOf());  //得到现在时间距离1970.1.1总的毫秒数
console.log(date.getTime());

// 2.简单的写法
var date1 = +new Date();  // +new Date()返回的就是总的毫秒数，
console.log(date1);

// 3. HTML5中提供的方法 获得总的毫秒数 有兼容性问题
console.log(Date.now());

```

### 数组对象

#### 数组对象的创建

创建数组对象的两种方式

```js
字面量方式
new Array()
```

#### 检测是否为数组

- instanceof 运算符，可以判断一个对象是否属于某种类型
- `Array.isArray()` 用于判断一个对象是否为数组，isArray() 是 HTML5 中提供的方法

```js
var arr = [1, 23];
var obj = {};
console.log(arr instanceof Array); // true
console.log(obj instanceof Array); // false
console.log(Array.isArray(arr));   // true
console.log(Array.isArray(obj));   // false
```

#### 添加删除数组元素

| 方法名          | 说明                                                  | 返回值               |
| --------------- | ----------------------------------------------------- | -------------------- |
| push(参数1…)    | 末尾添加一个或多个元素，注意修改原数组                | 并返回新的长度       |
| pop()           | 删除数组最后一个元素                                  | 返回它删除的元素的值 |
| unshift(参数1…) | 向数组的开头添加一个或更多元素，注意修改原数组        | 并返回新的长度       |
| shift()         | 删除数组的第一个元素，数组长度减1，无参数，修改原数组 | 并返回第一个元素     |

#### 数组排序

| 方法名    | 说明                         | 是否修改原数组                     |
| --------- | ---------------------------- | ---------------------------------- |
| reverse() | 颠倒数组中元素的顺序，无参数 | 该方法会改变原来的数组，返回新数组 |
| sort()    | 对数组的元素进行排序         | 该方法会改变原来的数组，返回新数组 |

#### 数组索引

| 方法名        | 说明                               | 返回值                                   |
| ------------- | ---------------------------------- | ---------------------------------------- |
| indexOf()     | 数组中查找给定元素的第一个索引     | 如果存在返回索引号，如果不存在，则返回-1 |
| lastIndexOf() | 在数组的最后一个索引，从后向前索引 | 如果存在返回索引号，如果不存在，则返回-1 |

#### 数组转化为字符串

| 方法名         | 说明                                       | 返回值         |
| -------------- | ------------------------------------------ | -------------- |
| toString()     | 把数组转换成字符串，逗号分隔每一项         | 返回一个字符串 |
| join(‘分隔符’) | 方法用于把数组中的所有元素转换为一个字符串 | 返回一个字符串 |

#### 其他方法

| 方法名   | 说明                                   | 返回值                                   |
| -------- | -------------------------------------- | ---------------------------------------- |
| concat() | 连接两个或多个数组 不影响原数组        | 返回一个新的数组                         |
| slice()  | 数组截取slice(begin,end)               | 返回被截取项目的新数组                   |
| splice() | 数组删除splice(第几个开始要删除的个数) | 返回被删除项目的新数组，这个会影响原数组 |

### 字符串对象

#### 基本包装类型

为了方便操作基本数据类型，JavaScript 还提供了三个特殊的引用类型：String、Number和 Boolean。

**基本包装类型**

就是把简单数据类型包装成为复杂数据类型，这样基本数据类型就有了属性和方法。

我们看看下面代码有什么问题吗？

```js
var str = 'andy';
console.log(str.length);
```

按道理基本数据类型是没有属性和方法的，而对象才有属性和方法，但上面代码却可以执行，这是因为 js 会把基本数据类型包装为复杂数据类型，其执行过程如下 ：

```js
// 1.生成临时变量,把简单类型包装为复杂数据类型
var temp = new String('andy');
// 2.赋值给我们声明的字符变量
str = temp;
// 3.销毁临时变量
temp = null;
```

#### 字符串的不可变

指的是里面的值不可变，虽然看上去可以改变内容，但其实是地址变了，内存中新开辟了一个内存空间。

#### 根据字符返回位置

字符串所有的方法，都不会修改字符串本身(字符串是不可变的)，**操作完成会返回一个新的字符串**

| 方法名                              | 说明                                                         |
| ----------------------------------- | ------------------------------------------------------------ |
| indexOf(‘要查找的字符’，开始的位置) | 返回指定内容在元字符串中的位置，如果找不到就返回-1，开始的位置是index索引号 |
| lastIndexOf()                       | 从后往前找，只找第一个匹配的                                 |

#### 根据位置返回字符

| 方法名            | 说明                                     | 使用                        |
| ----------------- | ---------------------------------------- | --------------------------- |
| charAt(index)     | 返回指定位置的字符(index字符串的索引号)  | str.charAt(0)               |
| charCodeAt(index) | 获取指定位置处字符的ASCII码(index索引号) | str.charCodeAt(0)           |
| str[index]        | 获取指定位置处字符                       | HTML,IE8+支持和charAt()等效 |

#### 字符串操作方法

| 方法名                   | 说明                                                         |
| ------------------------ | ------------------------------------------------------------ |
| concat(str1,str2,str3…)🔥 | concat() 方法用于连接两个或对各字符串。拼接字符串🔥           |
| substr(start,length)🔥    | 从 start 位置开始(索引号), length 取的个数。🔥                |
| slice(start,end)         | 从 start 位置开始，截取到 end 位置 ，end 取不到 (两个都是索引号) |
| substring(start,end)     | 从 start 位置开始，截取到 end 位置 ，end 取不到 (基本和 slice 相同，但是不接受负) |

#### replace()方法

replace() 方法用于在字符串中用一些字符替换另一些字符

其使用格式：`replace(被替换的字符,要替换为的字符串)`

#### split()方法

split() 方法用于切分字符串，它可以将字符串切分为数组。在切分完毕之后，返回的是一个新数组。

#### 大小写转换

- `toUpperCase()` 转换大写
- `toLowerCase()` 转换小写

### 简单类型与复杂类型

简单类型又叫做基本数据类型或者值类型，复杂类型又叫做引用类型。

1：值类型：简单数据类型/基本数据类型，在存储时变量中存储的是值本身，因此叫做值类型   

- string ，number，boolean，undefined，null

2：引用类型：复杂数据类型，在存储时变量中存储的仅仅是地址（引用），因此叫做引用数据类型   

- 通过 new 关键字创建的对象（系统对象、自定义对象），如 Object、Array、Date等

### 堆和栈

栈（操作系统）：由操作系统自动分配释放存放函数的参数值、局部变量的值等。其操作方式类似于数据结构中的栈；   

- 简单数据类型存放到栈里面

堆（操作系统）：存储复杂类型(对象)，一般由程序员分配释放，若程序员不释放，由垃圾回收机制回收。   

- 复杂数据类型存放到堆里面

![](https://img-blog.csdnimg.cn/ec62026538be449cb9c639f1fa54c844.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L0F1Z2Vuc3Rlcm5fUVhM,size_16,color_FFFFFF,t_70#pic_center)



注意：JavaScript中没有堆栈的概念，通过堆栈的方式，可以让大家更容易理解代码的一些执行方式，便于将来学习其他语言。

```js
<script>
// 简单数据类型 null  返回的是一个空的对象  object 
var timer = null;
console.log(typeof timer);
// 如果有个变量我们以后打算存储为对象，暂时没想好放啥， 这个时候就给 null 
// 1. 简单数据类型 是存放在栈里面 里面直接开辟一个空间存放的是值
// 2. 复杂数据类型 首先在栈里面存放地址 十六进制表示  然后这个地址指向堆里面的数据
</script>
```
#### 简单类型传参

函数的形参也可以看做是一个变量，当我们把一个值类型变量作为参数传给函数的形参时，其实是把变量在栈空间里的值复制了一份给形参，那么在方法内部对形参做任何修改，都不会影响到的外部变量。
```js
<script>
    // 简单数据类型传参
    function fn(a) {
        a++;
        console.log(a);
    }
    var x = 10;
    fn(x);
    console.log(x);
</script>
```
#### 复杂类型传参

函数的形参也可以看做是一个变量，当我们把引用类型变量传给形参时，其实是把变量在栈空间里保存的堆地址复制给了形参，形参和实参其实保存的是同一个堆地址，所以操作的是同一个对象。

```js
<script>
    // 复杂数据类型传参
    function Person(name) {
        this.name = name;
    }
function f1(x) { // x = p
    console.log(x.name); // 2. 这个输出什么 ?  刘德华   
    x.name = "张学友";
    console.log(x.name); // 3. 这个输出什么 ?   张学友
}
var p = new Person("刘德华");
console.log(p.name); // 1. 这个输出什么 ?   刘德华 
f1(p);
console.log(p.name); // 4. 这个输出什么 ?   张学友
</script>
```

### DOM

#### 什么是DOM

文档对象模型（Document Object Model，简称 DOM），是 W3C 组织推荐的处理可扩展标记语言（HTML或者XML）的标准编程接口

W3C 已经定义了一系列的 DOM 接口，通过这些 DOM 接口可以改变网页的内容、结构和样式。

![](https://img-blog.csdnimg.cn/fc42557d25be4683881c2f0f231bc778.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L0F1Z2Vuc3Rlcm5fUVhM,size_16,color_FFFFFF,t_70#pic_center)





- 文档：一个页面就是一个文档，DOM中使用doucument来表示
- 元素：页面中的所有标签都是元素，DOM中使用 element 表示
- 节点：网页中的所有内容都是节点（标签，属性，文本，注释等），DOM中使用node表示

DOM 把以上内容都看做是对象

#### 获取元素

##### 如何获取页面元素

DOM在我们实际开发中主要用来操作元素。

我们如何来获取页面中的元素呢?

获取页面中的元素可以使用以下几种方式:

- 根据 ID 获取
- 根据标签名获取
- 通过 HTML5 新增的方法获取
- 特殊元素获取

#### 根据ID获取

使用 `getElementByld()` 方法可以获取带ID的元素对象

```js
doucument.getElementByld('id名')
```

使用 `console.dir()` 可以打印我们获取的元素对象，更好的查看对象里面的属性和方法。

#### 根据标签名获取

根据**标签名**获取，使用 `getElementByTagName()` 方法可以返回带有指定标签名的**对象的集合**

```js
doucument.getElementsByTagName('标签名');
```

- 因为得到的是一个对象的集合，所以我们想要操作里面的元素就需要遍历
- 得到元素对象是动态的
- 返回的是获取过来元素对象的集合，以伪数组的形式存储
- 如果获取不到元素，则返回为空的伪数组(因为获取不到对象)

#### 根据标签名获取

还可以根据标签名获取某个元素（父元素）内部所有指定标签名的子元素,获取的时候不包括父元素自己

```js
element.getElementsByTagName('标签名')

ol.getElementsByTagName('li');
```

注意：父元素必须是单个对象(必须指明是哪一个元素对象)，获取的时候不包括父元素自己


```js
//element.getElementsByTagName('标签名'); 父元素必须是指定的单个元素
var ol = document.getElementById('ol');
console.log(ol[0].getElementsByTagName('li'));
```

#### 通过H5新增方法获取

##### ①getElementsByClassName

根据类名返回元素对象合集

- `document.getElementsByClassName('类名')`

```js
document.getElementsByClassName('类名'); 
```

##### ②document.querySelector

根据指定选择器返回第一个元素对象

```js
document.querySelector('选择器');

// 切记里面的选择器需要加符号 
// 类选择器.box 
// id选择器 #nav
var firstBox = document.querySelector('.box');
```

##### ③document.querySelectorAll

根据指定选择器返回所有元素对象

```js
document.querySelectorAll('选择器');
```

注意：

```
querySelector` 和 `querySelectorAll` 里面的选择器需要加符号,比如: `document.querySelector('#nav');
```

##### ④例子

```js
// 1. getElementsByClassName 根据类名获得某些元素集合
    var boxs = document.getElementsByClassName('box');
    console.log(boxs);
    // 2. querySelector 返回指定选择器的第一个元素对象  切记 里面的选择器需要加符号 .box  #nav
    var firstBox = document.querySelector('.box');
    console.log(firstBox);
    var nav = document.querySelector('#nav');
    console.log(nav);
    var li = document.querySelector('li');
    console.log(li);
    // 3. querySelectorAll()返回指定选择器的所有元素对象集合
    var allBox = document.querySelectorAll('.box');
    console.log(allBox);
    var lis = document.querySelectorAll('li');
    console.log(lis);
```

#### 获取特殊元素

##### ①获取body元素

返回body元素对象

```js
document.body;
```

##### ②获取html元素

返回html元素对象

```js
document.documentElement;
```

### 事件基础

#### 事件概述

JavaScript 使我们有能力创建动态页面，而事件是可以被 JavaScript 侦测到的行为。

简单理解： 触发— 响应机制。

网页中的每个元素都可以产生某些可以触发 JavaScript 的事件，例如，我们可以在用户点击某按钮时产生一个事件，然后去执行某些操作。

#### 事件三要素

1. 事件源(谁)
2. 事件类型(什么事件)
3. 事件处理程序(做啥)

#### 执行事件的步骤

1. 获取事件源
2. 注册事件(绑定事件)
3. 添加事件处理程序(采取函数赋值形式)

### 鼠标事件

| 鼠标事件    | 触发条件         |
| ----------- | ---------------- |
| onclick     | 鼠标点击左键触发 |
| onmouseover | 鼠标经过触发     |
| onmouseout  | 鼠标离开触发     |
| onfocus     | 获得鼠标焦点触发 |
| onblur      | 失去鼠标焦点触发 |

#### 操作元素

JavaScript 的 DOM 操作可以改变网页内容、结构和样式，我们可以利用 DOM 操作元素来改变元素里面的内容 、属性等。注意以下都是属性

#### 改变元素内容

从起始位置到终止位置的内容，但它去除html标签，同时空格和换行也会去掉。

```js
element.innerText
```

起始位置到终止位置的全部内容，包括HTML标签，同时保留空格和换行

```js
element.innerHTML
```

```html
<body>
    <div></div>
    <p>
        我是文字
        <span>123</span>
    </p>

    <script>
        // innerText 和 innerHTML的区别 
        // 1. innerText 不识别html标签,去除空格和换行
        var div = document.querySelector('div');
        div.innerText = '<strong>今天是：</strong> 2019';
        // 2. innerHTML 识别html标签 保留空格和换行的
        div.innerHTML = '<strong>今天是：</strong> 2019';
        // 这两个属性是可读写的  可以获取元素里面的内容
        var p = document.querySelector('p');
        console.log(p.innerText);
        console.log(p.innerHTML);
    </script>
</body>

```

#### 改变元素属性

```js
// img.属性
img.src = "xxx";

input.value = "xxx";
input.type = "xxx";
input.checked = "xxx";
input.selected = true / false;
input.disabled = true / false;
```

#### 改变样式属性

我们可以通过 JS 修改元素的大小、颜色、位置等样式。

- 行内样式操作

```js
// element.style
div.style.backgroundColor = 'pink';
div.style.width = '250px';
```

- 类名样式操作

```js
// element.className
```

注意：

```js
JS里面的样式采取驼峰命名法，比如 fontSize ，backgroundColor
JS 修改 style 样式操作 ，产生的是行内样式，CSS权重比较高
如果样式修改较多，可以采取操作类名方式更改元素样式
class 因为是个保留字，因此使用className来操作元素类名属性
className 会直接更改元素的类名，会覆盖原先的类名
```
#### 总结

![](https://img-blog.csdnimg.cn/f6835ead437948e3804c4432ceb812ad.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L0F1Z2Vuc3Rlcm5fUVhM,size_16,color_FFFFFF,t_70#pic_center)

### 排他思想

如果有同一组元素，我们相要某一个元素实现某种样式，需要用到循环的排他思想算法：

1. 所有元素全部清除样式（干掉其他人）
2. 给当前元素设置样式 （留下我自己）
3. 注意顺序不能颠倒，首先干掉其他人，再设置自己

```html
<body>
    <button>按钮1</button>
    <button>按钮2</button>
    <button>按钮3</button>
    <button>按钮4</button>
    <button>按钮5</button>
    <script>
        // 1. 获取所有按钮元素
        var btns = document.getElementsByTagName('button');
        // btns得到的是伪数组  里面的每一个元素 btns[i]
        for (var i = 0; i < btns.length; i++) {
            btns[i].onclick = function() {
                // (1) 我们先把所有的按钮背景颜色去掉  干掉所有人
                for (var i = 0; i < btns.length; i++) {
                    btns[i].style.backgroundColor = '';
                }
                // (2) 然后才让当前的元素背景颜色为pink 留下我自己
                this.style.backgroundColor = 'pink';

            }
        }
        //2. 首先先排除其他人，然后才设置自己的样式 这种排除其他人的思想我们成为排他思想
    </script>
</body>

```

### 自定义属性

#### 获取属性值

- 获取内置属性值(元素本身自带的属性)

```js
element.属性;
```

- 获取自定义的属性

```
element.getAttribute('属性');
```

#### 设置属性值

- 设置内置属性值

```
element.属性 = '值';
```

- 主要设置自定义的属性

```js
element.setAttribute('属性','值');
```

#### 移除属性

```js
element.removeAttribute('属性');
```

### H5自定义属性

自定义属性目的：

- 保存并保存数据，有些数据可以保存到页面中而不用保存到数据库中
- 有些自定义属性很容易引起歧义，不容易判断到底是内置属性还是自定义的，所以H5有了规定

#### 设置H5自定义属性

H5规定自定义属性 `data-`开头作为属性名并赋值

```js
<div data-index = "1"></>
// 或者使用JavaScript设置
div.setAttribute('data-index',1);
```

#### 获取H5自定义属性

- 兼容性获取 `element.getAttribute('data-index')`
- H5新增的：`element.dataset.index` 或`element.dataset['index']` IE11才开始支持

```html
<body>
    <div getTime="20" data-index="2" data-list-name="andy"></div>
    <script>
        var div = document.querySelector('div');
        console.log(div.getAttribute('getTime'));
        div.setAttribute('data-time', 20);
        console.log(div.getAttribute('data-index'));
        console.log(div.getAttribute('data-list-name'));
        // h5新增的获取自定义属性的方法 它只能获取data-开头的
        // dataset 是一个集合里面存放了所有以data开头的自定义属性
        console.log(div.dataset);
        console.log(div.dataset.index);
        console.log(div.dataset['index']);
        // 如果自定义属性里面有多个-链接的单词，我们获取的时候采取 驼峰命名法
        console.log(div.dataset.listName);
        console.log(div.dataset['listName']);
    </script>
</body>
```

### 节点操作

获取元素通常使用两种方式：

| 1.利用DOM提供的方法获取元素     | 2.利用节点层级关系获取元素 |
| ------------------------------- | -------------------------- |
| document.getElementById()       | 利用父子兄节点关系获取元素 |
| document.getElementsByTagName() | 逻辑性强，但是兼容性较差   |
| document.querySelector 等       |                            |
| 逻辑性不强，繁琐                |                            |

这两种方式都可以获取元素节点，我们后面都会使用，但是节点操作更简单

一般的，节点至少拥有三个基本属性

#### 节点概述

网页中的所有内容都是节点（标签、属性、文本、注释等），在DOM 中，节点使用 node 来表示。

HTML DOM 树中的所有节点均可通过 JavaScript 进行访问，所有 HTML 元素（节点）均可被修改，也可以创建或删除。

一般的，节点至少拥有nodeType（节点类型）、nodeName（节点名称）和nodeValue（节点值）这三个基本属性。

元素节点：nodeType 为1
属性节点：nodeType 为2
文本节点：nodeType 为3(文本节点包括文字、空格、换行等)

我们在实际开发中，节点操作主要操作的是元素节点

利用 DOM 树可以把节点划分为不同的层级关系，常见的是父子兄层级关系。

#### 父级节点

```js
node.parentNode
```

- `parentNode`属性可以返回某节点的父结点，注意是最近的一个父结点
- 如果指定的节点没有父结点则返回null

#### 子结点

```js
parentNode.childNodes(标准)
```

- `parentNode.childNodes` 返回包含指定节点的子节点的集合，该集合为即时更新的集合
- 返回值包含了所有的子结点，包括元素节点，文本节点等
- 如果只想要获得里面的元素节点，则需要专门处理。所以我们一般不提倡使用`childNodes`

```js
parentNode.children(非标准)
```

- `parentNode.children` 是一个只读属性，返回所有的子元素节点
- 它只返回子元素节点，其余节点不返回 （**这个是我们重点掌握的**）
- 虽然 children 是一个非标准，但是得到了各个浏览器的支持，因此我们可以放心使用

##### 第一个子结点

```js
parentNode.firstChild
```

- `firstChild` 返回第一个子节点，找不到则返回null
- 同样，也是包含所有的节点

##### 最后一个子结点

```js
parentNode.lastChild
```

- `lastChild` 返回最后一个子节点，找不到则返回null
- 同样，也是包含所有的节点

##### 第一个子结点(兼容性)

```js
parentNode.firstElementChild
1
```

- `firstElementChild` 返回第一个子节点，找不到则返回null
- 有兼容性问题，IE9以上才支持

##### 最后一个子结点(兼容性)

```js
parentNode.lastElementChild
```

- `lastElementChild` 返回最后一个子节点，找不到则返回null
- 有兼容性问题，IE9以上才支持

#### 解决方案

实际开发中，firstChild 和 lastChild 包含其他节点，操作不方便，而 firstElementChild 和 lastElementChild 又有兼容性问题，那么我们如何获取第一个子元素节点或最后一个子元素节点呢？

如果想要第一个子元素节点，可以使用 `parentNode.chilren[0]`

如果想要最后一个子元素节点，可以使用

```js
// 数组元素个数减1 就是最后一个元素的索引号
parentNode.chilren[parentNode.chilren.length - 1]
```

#### 兄弟节点

##### 下一个兄弟节点

```js
node.nextSibling
```

- `nextSibling` 返回当前元素的下一个兄弟元素节点，找不到则返回null
- 同样，也是包含所有的节点

##### 上一个兄弟节点

```js
node.previousSibling
```

- `previousSibling` 返回当前元素上一个兄弟元素节点，找不到则返回null
- 同样，也是包含所有的节点

##### 下一个兄弟节点(兼容性)

```js
node.nextElementSibling
```

- `nextElementSibling` 返回当前元素下一个兄弟元素节点，找不到则返回null
- 有兼容性问题，IE9才支持

##### 上一个兄弟节点(兼容性)

```js
node.previousElementSibling
```

- `previousElementSibling` 返回当前元素上一个兄弟元素节点，找不到则返回null
- 有兼容性问题，IE9才支持

#### **如何解决兼容性问题 ？**

答：自己封装一个兼容性的函数

### 创建节点

```js
document.createElement('tagName');
```

- `document.createElement()` 方法创建由 tagName 指定的HTML 元素
- 因为这些元素原先不存在，是根据我们的需求动态生成的，所以我们也称为**动态创建元素节点**

##### 添加节点

```js
node.appendChild(child)
```

`node.appendChild()` 方法将一个节点添加到指定父节点的子节点列表**末尾**。类似于 CSS 里面的 after 伪元素。

```js
node.insertBefore(child,指定元素)
```

`node.insertBefore()` 方法将一个节点添加到父节点的指定子节点**前面**。类似于 CSS 里面的 before 伪元素。

##### 删除节点

```js
node.removeChild(child)
```

`node.removeChild()`方法从 DOM 中删除一个子节点，返回删除的节点

##### 复制节点(克隆节点)

```js
node.cloneNode()
```

- `node.cloneNode()`方法返回调用该方法的节点的一个副本。 也称为克隆节点/拷贝节点
- 如果括号参数为空或者为 false ，则是浅拷贝，即只克隆复制节点本身，不克隆里面的子节点
- 如果括号参数为 true ，则是深度拷贝，会复制节点本身以及里面所有的子节点

#### 面试题

三种动态创建元素的区别

- oucument.write()
- lement.innerHTML
- ocument.createElement()

区别：

   - document.write() 是直接将内容写入页面的内容流，但是文档流执行完毕，则它会导致页面全部重绘
   - innerHTML 是将内容写入某个 DOM 节点，不会导致页面全部重绘
   - innerHTML 创建多个元素效率更高（不要拼接字符串，采取数组形式拼接），结构稍微复杂
- `createElement()`创建多个元素效率稍低一点点，但是结构更清晰

> 总结：不同浏览器下， innerHTML 效率要比 createElement 高

### DOM核心

对于DOM操作，我们主要针对子元素的操作，主要有

- 创建
- 增
- 删
- 改
- 查
- 属性操作
- 时间操作

#### 创建

- document.write
- innerHTML
- createElement

#### 增

- appendChild
- insertBefore

#### 删

- removeChild

#### 改

- 主要修改dom的元素属性，dom元素的内容、属性、表单的值等
 - 修改元素属性：src、href、title 等
 - 修改普通元素内容：innerHTML、innerText
  - 修改表单元素：value、type、disabled
- 修改元素样式：style、className

#### 查

- 主要获取查询dom的元素
 - DOM提供的API方法：getElementById、getElementsByTagName (古老用法，不推荐)
 - H5提供的新方法：querySelector、querySelectorAll (提倡)
 - 利用节点操作获取元素：父(parentNode)、子(children)、兄(previousElementSibling、nextElementSibling) 提倡

#### 属性操作

- 主要针对于自定义属性
    - setAttribute：设置dom的属性值
    - getAttribute：得到dom的属性值
    - removeAttribute：移除属性
### 类名操作

1.使用classList返回所选元素的类名，是一个数组，一个类名占一个长度(a.classList.length)。

2.a.classList.add("classname1") ; 添加一个类名

3.a.classList.remove("classname2") ; 去掉一个类名

4.a.classLis.toggle("classname3"); 引号中的类名，有就删除，没有就添加。比较智能的结合了1,2点，用于切换十分方便

5.a.contains("classname4"); 判断一个类型是不是存在，返回true和false



### 事件高级

#### 注册事件(绑定事件)

给元素添加事件，称为注册事件或者绑定事件。

注册事件有两种方式：传统方式和方法监听注册方式

| 传统注册方式                                                 | 方法监听注册方式                                      |
| ------------------------------------------------------------ | ----------------------------------------------------- |
| 利用 on 开头的事件 onclick                                   | w3c 标准推荐方式                                      |
| `<button onclick = "alert("hi")"></button>`                  | addEventListener() 它是一个方法                       |
| btn.onclick = function() {}                                  | IE9 之前的 IE 不支持此方法，可使用 attachEvent() 代替 |
| 特点：注册事件的唯一性                                       | 特点：同一个元素同一个事件可以注册多个监听器          |
| 同一个元素同一个事件只能设置一个处理函数，最后注册的处理函数将会覆盖前面注册的处理函数 | 按注册顺序依次执行                                    |

#### ①addEventListener事件监听方式

- eventTarget.addEventListener()方法将指定的监听器注册到 eventTarget（目标对象）上
- 当该对象触发指定的事件时，就会执行事件处理函数

```js
eventTarget.addEventListener(type,listener[,useCapture])
```

 该方法接收三个参数：

- `type`:事件类型字符串，比如click,mouseover,注意这里不要带on
- `listener`：事件处理函数，事件发生时，会调用该监听函数
- `useCapture`：可选参数，是一个布尔值，默认是 false。学完 DOM 事件流后，我们再进一步学习

#### attachEvent事件监听方式(兼容)

- eventTarget.attachEvent()方法将指定的监听器注册到 eventTarget（目标对象） 上
- 当该对象触发指定的事件时，指定的回调函数就会被执行

```js
eventTarget.attachEvent(eventNameWithOn,callback)
```

**addEventListener（'click',fn）；（fn后不用加小括号）**

该方法接收两个参数：

```js
eventNameWithOn：事件类型字符串，比如 onclick 、onmouseover ，这里要带 on
callback： 事件处理函数，当目标触发事件时回调函数被调用
ie9以前的版本支持
```
#### ③注册事件兼容性解决方案

```js
 function addEventListener(element, eventName, fn) {
      // 判断当前浏览器是否支持 addEventListener 方法
      if (element.addEventListener) {
        element.addEventListener(eventName, fn);  // 第三个参数 默认是false
      } else if (element.attachEvent) {
        element.attachEvent('on' + eventName, fn);
      } else {
        // 相当于 element.onclick = fn;
        element['on' + eventName] = fn;
 } 
```

#### 删除事件(解绑事件)

#### removeEventListener删除事件方式

```js
eventTarget.removeEventListener(type,listener[,useCapture]);
```

#### detachEvent删除事件方式(兼容)

```js
eventTarget.detachEvent(eventNameWithOn,callback);
```

#### 传统事件删除方式

```js
eventTarget.onclick = null;
```

### DOM事件流

- 事件流描述的是从页面中接收事件的顺序
- 事件发生时会在元素节点之间按照特定的顺序传播，这个传播过程即DOM事件流

![在这里插入图片描述](https://img-blog.csdnimg.cn/063297f2336f43dfb246930ae877a9ad.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L0F1Z2Vuc3Rlcm5fUVhM,size_16,color_FFFFFF,t_70#pic_center)

- 事件冒泡： IE 最早提出，事件开始时由最具体的元素接收，然后逐级向上传播到到 DOM 最顶层节点的过程。

- 事件捕获： 网景最早提出，由 DOM 最顶层节点开始，然后逐级向下传播到到最具体的元素接收的过程。

  **加深理解**：

  我们向水里面扔一块石头，首先它会有一个下降的过程，这个过程就可以理解为从最顶层向事件发生的最具体元素（目标点）的捕获过程；之后会产生泡泡，会在最低点（ 最具体元素）之后漂浮到水面上，这个过程相当于事件冒泡。

  ![在这里插入图片描述](https://img-blog.csdnimg.cn/51f0146f0e334813b35d9b7075382a33.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L0F1Z2Vuc3Rlcm5fUVhM,size_16,color_FFFFFF,t_70#pic_center)

#### 捕获阶段

document -> html -> body -> father -> son

两个盒子嵌套，一个父盒子一个子盒子，我们的需求是当点击父盒子时弹出 father ，当点击子盒子时弹出 son

```js
<body>
    <div class="father">
        <div class="son">son盒子</div>
    </div>
    <script>
        // dom 事件流 三个阶段
        // 1. JS 代码中只能执行捕获或者冒泡其中的一个阶段。
        // 2. onclick 和 attachEvent（ie） 只能得到冒泡阶段。
        // 3. 捕获阶段 如果addEventListener 第三个参数是 true 那么则处于捕获阶段  document -> html -> body -> father -> son
        var son = document.querySelector('.son');
        son.addEventListener('click', function() {
             alert('son');
        }, true);
        var father = document.querySelector('.father');
        father.addEventListener('click', function() {
            alert('father');
        }, true);
    </script>
</body>

```

但是因为DOM流的影响，我们点击子盒子，会先弹出 father，之后再弹出 son

这是因为捕获阶段由 DOM 最顶层节点开始，然后逐级向下传播到到最具体的元素接收

document -> html -> body -> father -> son

先看 document 的事件，没有；再看 html 的事件，没有；再看 body 的事件，没有；再看 father 的事件，有就先执行；再看 son 的事件，再执行。

#### 冒泡阶段

son -> father ->body -> html -> document

```html
<body>
    <div class="father">
        <div class="son">son盒子</div>
    </div>
    <script>
		// 4. 冒泡阶段 如果addEventListener 第三个参数是 false 或者 省略 那么则处于冒泡阶段  son -> father ->body -> html -> document
        var son = document.querySelector('.son');
        son.addEventListener('click', function() {
            alert('son');
        }, false);
        var father = document.querySelector('.father');
        father.addEventListener('click', function() {
            alert('father');
        }, false);
        document.addEventListener('click', function() {
            alert('document');
        })
    </script>
</body>

```

我们点击子盒子，会弹出 son、father、document

这是因为冒泡阶段开始时由最具体的元素接收，然后逐级向上传播到到 DOM 最顶层节点

- son -> father ->body -> html -> document

#### 小结

JS 代码中只能执行捕获或者冒泡其中的一个阶段

onclick 和 attachEvent只能得到冒泡阶段

addEventListener(type,listener[,useCapture])第三个参数如果是 true，表示在事件捕获阶段调用事件处理程序；如果是 false (不写默认就是false),表示在事件冒泡阶段调用事件处理程序

实际开发中我们很少使用事件捕获，我们更关注事件冒泡。

有些事件是没有冒泡的，比如 onblur、onfocus、onmouseenter、onmouseleave

### 事件对象

```js
eventTarget.onclick = function(event) {
   // 这个 event 就是事件对象，我们还喜欢的写成 e 或者 evt 
} 
eventTarget.addEventListener('click', function(event) {
   // 这个 event 就是事件对象，我们还喜欢的写成 e 或者 evt  
})
```

官方解释：event 对象代表事件的状态，比如键盘按键的状态、鼠标的位置、鼠标按钮的状态
简单理解：

事件发生后，跟事件相关的一系列信息数据的集合都放到这个对象里面
这个对象就是事件对象 event，它有很多属性和方法，比如“
    谁绑定了这个事件
    鼠标触发事件的话，会得到鼠标的相关信息，如鼠标位置
    键盘触发事件的话，会得到键盘的相关信息，如按了哪个键

这个 event 是个形参，系统帮我们设定为事件对象，不需要传递实参过去
当我们注册事件时， event 对象就会被系统自动创建，并依次传递给事件监听器（事件处理函数）

#### 事件对象的兼容性方案

事件对象本身的获取存在兼容问题：

1. 标准浏览器中是浏览器给方法传递的参数，只需要定义形参 e 就可以获取到。
2. 在 IE6~8 中，浏览器不会给方法传递参数，如果需要的话，需要到 window.event 中获取查找

解决：

```js
e = e || window.event;
```

#### 事件对象的常见属性和方法

| 事件对象属性方法    | 说明                                          |
| ------------------- | --------------------------------------------- |
| e.target            | 返回触发事件的对象 标准                       |
| e.srcElement        | 返回触发事件的对象 非标准 ie6-8使用           |
| e.type              | 返回事件的类型 比如`click` `mouseover` 不带on |
| e.cancelBubble      | 该属性阻止冒泡，非标准，ie6-8使用             |
| e.returnValue       | 该属性阻止默认行为 非标准，ie6-8使用          |
| e.preventDefault()  | 该方法阻止默认行为 标准 比如不让链接跳转      |
| e.stopPropagation() | 阻止冒泡 标准                                 |

e.target 和 this 的区别：

- this 是事件绑定的元素， 这个函数的调用者（绑定这个事件的元素）
- e.target 是事件触发的元素。

```html
<body>
    <div>123</div>
    <ul>
        <li>abc</li>
        <li>abc</li>
        <li>abc</li>
    </ul>
    <script>
        // 常见事件对象的属性和方法
        // 1. e.target 返回的是触发事件的对象（元素）  this 返回的是绑定事件的对象（元素）
        // 区别 ： e.target 点击了那个元素，就返回那个元素 this 那个元素绑定了这个点击事件，那么就返回谁
        var div = document.querySelector('div');
        div.addEventListener('click', function(e) {
            console.log(e.target);
            console.log(this);
```

```html
<body>
    <div>123</div>
    <ul>
        <li>abc</li>
        <li>abc</li>
        <li>abc</li>
    </ul>
    <script>
        // 常见事件对象的属性和方法
        // 1. e.target 返回的是触发事件的对象（元素）  this 返回的是绑定事件的对象（元素）
        // 区别 ： e.target 点击了那个元素，就返回那个元素 this 那个元素绑定了这个点击事件，那么就返回谁
        var div = document.querySelector('div');
        div.addEventListener('click', function(e) {
            console.log(e.target);
            console.log(this);

        })
        var ul = document.querySelector('ul');
        ul.addEventListener('click', function(e) {
                // 我们给ul 绑定了事件  那么this 就指向ul  
                console.log(this);
                console.log(e.currentTarget);

                // e.target 指向我们点击的那个对象 谁触发了这个事件 我们点击的是li e.target 指向的就是li
                console.log(e.target);

            })
            // 了解兼容性
            // div.onclick = function(e) {
            //     e = e || window.event;
            //     var target = e.target || e.srcElement;
            //     console.log(target);

        // }
        // 2. 了解 跟 this 有个非常相似的属性 currentTarget  ie678不认识
    </script>
</body>

```
#### 事件对象阻止默认行为

```js
e.preventDefault()
```

#### 阻止事件冒泡

事件冒泡：开始时由最具体的元素接收，然后逐级向上传播到到 DOM 最顶层节点

事件冒泡本身的特性，会带来的坏处，也会带来的好处，需要我们灵活掌握。

- 标准写法

```js
e.stopPropagation();
```

### 事件委托

- 事件委托也称为事件代理，在 jQuery 里面称为事件委派
- 事件委托的原理
  - **不是每个子节点单独设置事件监听器，而是事件监听器设置在其父节点上，然后利用冒泡原理影响设置每个子节点**

```html
<body>
    <ul>
        <li>知否知否，点我应有弹框在手！</li>
        <li>知否知否，点我应有弹框在手！</li>
        <li>知否知否，点我应有弹框在手！</li>
        <li>知否知否，点我应有弹框在手！</li>
        <li>知否知否，点我应有弹框在手！</li>
    </ul>
    <script>
        // 事件委托的核心原理：给父节点添加侦听器， 利用事件冒泡影响每一个子节点
        var ul = document.querySelector('ul');
        ul.addEventListener('click', function(e) {
            // alert('知否知否，点我应有弹框在手！');
            // e.target 这个可以得到我们点击的对象
            e.target.style.backgroundColor = 'pink';
            // 点了谁，就让谁的style里面的backgroundColor颜色变为pink
        })
    </script>
</body>
```

以上案例：给 ul 注册点击事件，然后利用事件对象的 target 来找到当前点击的 li，因为点击 li，事件会冒泡到 ul 上， ul 有注册事件，就会触发事件监听器。

#### 常见的鼠标事件

| onclick     | 鼠标点击左键触发 |
| ----------- | ---------------- |
| onmouseover | 鼠标经过触发     |
| onmouseout  | 鼠标离开触发     |
| onfocus     | 获得鼠标焦点触发 |
| onblur      | 失去鼠标焦点触发 |
| onmousemove | 鼠标移动触发     |
| onmouseup   | 鼠标弹起触发     |
| onmousedown | 鼠标按下触发     |

#### 禁止鼠标右键与鼠标选中

- `contextmenu`主要控制应该何时显示上下文菜单，主要用于程序员取消默认的上下文菜单
- `selectstart` 禁止鼠标选中

```html
<body>
    <h1>我是一段不愿意分享的文字</h1>
    <script>
        // 1. contextmenu 我们可以禁用右键菜单
        document.addEventListener('contextmenu', function(e) {
                e.preventDefault(); // 阻止默认行为
            })
            // 2. 禁止选中文字 selectstart
        document.addEventListener('selectstart', function(e) {
            e.preventDefault();

        })
    </script>
</body>
```

#### 鼠标事件对象

- **event**对象代表事件的状态，跟事件相关的一系列信息的集合
- 现阶段我们主要是用鼠标事件对象 **MouseEvent** 和键盘事件对象 **KeyboardEvent。**

| 鼠标事件对象    | 说明                                      |
| --------------- | ----------------------------------------- |
| e.clientX       | 返回鼠标相对于浏览器窗口**可视区**的X坐标 |
| e.clientY       | 返回鼠标相对于浏览器窗口**可视区**的Y坐标 |
| e.pageX（重点） | 返回鼠标相对于文档页面的X坐标 IE9+ 支持   |
| e.pageY（重点） | 返回鼠标相对于文档页面的Y坐标 IE9+ 支持   |
| e.screenX       | 返回鼠标相对于电脑屏幕的X坐标             |
| e.screenY       | 返回鼠标相对于电脑屏幕的Y坐标             |

#### 常用的键盘事件

| 键盘事件   | 触发条件                                                     |
| ---------- | ------------------------------------------------------------ |
| onkeyup    | 某个键盘按键被松开时触发                                     |
| onkeydown  | 某个键盘按键被按下时触发                                     |
| onkeypress | 某个键盘按键被按下时触发，但是它不识别功能键，比如 ctrl shift 箭头等 |

- **如果使用addEventListener 不需要加 on**
- `onkeypress` 和前面2个的区别是，它不识别功能键，比如左右箭头，shift 等
- 三个事件的执行顺序是： keydown – keypress — keyup

```html
 <body>
    <script>
        // 常用的键盘事件
        //1. keyup 按键弹起的时候触发 
        // document.onkeyup = function() {
        //         console.log('我弹起了');

        //     }
        document.addEventListener('keyup', function() {
            console.log('我弹起了');
        })
    
        //3. keypress 按键按下的时候触发  不能识别功能键 比如 ctrl shift 左右箭头啊
        document.addEventListener('keypress', function() {
                console.log('我按下了press');
            })
            //2. keydown 按键按下的时候触发  能识别功能键 比如 ctrl shift 左右箭头啊
        document.addEventListener('keydown', function() {
                console.log('我按下了down');
            })
            // 4. 三个事件的执行顺序  keydown -- keypress -- keyup
    </script>

</body>
```

#### 键盘对象属性

| 键盘事件对象 **属性** | 说明                    |
| --------------------- | ----------------------- |
| keyCode               | 返回该**键**值的ASCII值 |

- `onkeydown`和 `onkeyup` 不区分字母大小写，`onkeypress` 区分字母大小写。
- 在我们实际开发中，我们更多的使用keydown和keyup， 它能识别所有的键（包括功能键）
- `Keypress` 不识别功能键，但是`keyCode`属性能区分大小写，返回不同的ASCII值

```html
<body>
    <script>
        // 键盘事件对象中的keyCode属性可以得到相应键的ASCII码值
        // 1. 我们的keyup 和keydown事件不区分字母大小写  a 和 A 得到的都是65
        // 2. 我们的keypress 事件 区分字母大小写  a  97 和 A 得到的是65
        document.addEventListener('keyup', function(e) {
            console.log('up:' + e.keyCode);
            // 我们可以利用keycode返回的ASCII码值来判断用户按下了那个键
            if (e.keyCode === 65) {
                alert('您按下的a键');
            } else {
                alert('您没有按下a键')
            }

        })
        document.addEventListener('keypress', function(e) {
            console.log('press:' + e.keyCode);
        })
    </script>
</body>

```

### BOM概述

BOM = Browser Object Model 👉浏览器对象模型

它提供了独立于内容而与浏览器窗口进行交互的对象，其核心对象是 window

BOM 由一系列相关的对象构成，并且每个对象都提供了很多方法与属性

BOM 缺乏标准，JavaScript 语法的标准化组织是 ECMA, DOM 的标准化组织是 W3C, BOM最初是Netscape 浏览器标准的一部分

| DOM                                | BOM                                              |
| ---------------------------------- | ------------------------------------------------ |
| 文档对象模型                       | 浏览器对象模型                                   |
| DOM 就是把 文档 当作一个对象来看待 | 把 浏览器当作一个对象来看待                      |
| DOM 的顶级对象是 document          | BOM 的顶级对象是 window                          |
| DOM 主要学习的是操作页面元素       | BOM 学习的是浏览器窗口交互的一些对象             |
| DOM 是 W3C 标准规范                | BOM 是浏览器厂商在各自浏览器上定义的，兼容性较差 |

#### BOM的构成

![](https://img-blog.csdnimg.cn/5c83bf307ec9486687a5f52312943ecb.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L0F1Z2Vuc3Rlcm5fUVhM,size_16,color_FFFFFF,t_70#pic_center)

BOM 比 DOM 更大。它包含 DOM。

window 对象是浏览器的顶级对象，它具有双重角色

它是 JS 访问浏览器窗口的一个接口

它是一个全局对象。定义在全局作用域中的变量、函数都会变成 window 对象的属性和方法

在调用的时候可以省略 window，前面学习的对话框都属于 window 对象方法，如 alert()、prompt()等。

注意：window下的一个特殊属性 window.name

### window 对象的常见事件

#### 窗口加载事件

`window.onload`是窗口（页面）加载事件，当文档内容完全加载完成会触发该事件（包括图像，脚本文件，CSS文件等），就调用的处理函数。

```js
window.onload = function(){
    
};

// 或者
window.addEventListener("load",function(){});


```

有了window.onload就可以把JS代码写到页面元素的上方

因为onload是等页面内容全部加载完毕，再去执行处理函数

window.onload 传统注册事件方式，只能写一次

如果有多个，会以最后一个window.onload为准

如果使用addEventListener 则没有限制

```js
document.addEventListener('DOMContentLoaded',function(){})
```

接收两个参数：

- DOMCountentLoaded事件触发时，仅当DOM加载完成，不包括样式表，图片，flash等等
- 
- 如果页面的图片很多的话, 从用户访问到onload触发可能需要较长的时间
- 
- 交互效果就不能实现，必然影响用户的体验，此时用 DOMContentLoaded事件比较合适。
#### 区别

- `load`等页面内容全部加载完毕，包括页面dom元素，图片，flash，css等
- `DOMContentLoaded` 是DOM加载完毕，不包含图片 flash css 等就可以执行，加载速度比load更快一些

#### 调整窗口大小事件

`window.onresize` 是调整窗口大小加载事件，当触发时就调用的处理函数

```js
window.onresize = function() {}

// 或者
window.addEventListener('resize',function(){});
```

- 只要窗口大小发生像素变化，就会触发这个事件
- 我们经常利用这个事件完成响应式布局。`window.innerWidth` 当前屏幕的宽度

```HTML
<body>
    <script>
        window.addEventListener('load', function() {
            var div = document.querySelector('div');
            window.addEventListener('resize', function() {
                console.log(window.innerWidth);

                console.log('变化了');
                if (window.innerWidth <= 800) {
                    div.style.display = 'none';
                } else {
                    div.style.display = 'block';
                }
    
            })
        })
    </script>
    <div></div>
</body>
```

### 定时器

window 对象给我们提供了两个定时器

- `setTimeout()`
- `setInterval()`

#### setTimeout()定时器

`setTimeout()`方法用于设置一个定时器，该定时器在定时器到期后执行调用函数。

```js
window.setTimeout(调用函数,[延迟的毫秒数]);
```

注意：

   - window可以省略
   - 这个调用函数
   -    可以直接写函数
   -    或者写函数名
   -    或者采取字符串 ‘函数名()’ （不推荐）
   - 延迟的毫秒数省略默认是0，如果写，必须是毫秒
   - 因为定时器可能有很多，所以我们经常给定时器赋值一个标识符
   - setTimeout() 这个调用函数我们也称为回调函数 callback
   - 普通函数是按照代码顺序直接调用，而这个函数，需要等待事件，事件到了才会去调用这个函数，因此称为回调函数。
#### clearTimeout()停止定时器

- `clearTimeout()`方法取消了先前通过调用 `setTimeout()`建立的定时器

```js
window.clearTimeout(timeoutID)
```

**注意**：

- `window`可以省略
- 里面的参数就是定时器的标识符

#### setInterval()定时器

- `setInterval()`方法重复调用一个函数，每隔这个时间，就去调用一次回调函数

```js
window.setInterval(回调函数,[间隔的毫秒数]);
```

- `window`可以省略
- 这个回调函数:   
  - 可以直接写函数
  - 或者写函数名
  - 或者采取字符 ‘函数名()’
- 第一次执行也是间隔毫秒数之后执行，之后每隔毫秒数就执行一次

#### clearInterval()停止定时器

- `clearInterval ( )` 方法取消了先前通过调用 `setInterval()` 建立的定时器

**注意**：

- `window`可以省略
- 里面的参数就是定时器的标识符

### this指向

- `this`的指向在函数定义的时候是确定不了的，只有函数执行的时候才能确定`this`到底指向谁

现阶段，我们先了解一下几个this指向

​       全局作用域或者普通函数中`this`指向全局对象`window`(注意定时器里面的this指向window)

​       方法调用中谁调用`this`指向谁

​       构造函数中`this`指向构造函数实例

```html
<body>
    <button>点击</button>
    <script>
        // this 指向问题 一般情况下this的最终指向的是那个调用它的对象

        // 1. 全局作用域或者普通函数中this指向全局对象window（ 注意定时器里面的this指向window）
        console.log(this);

        function fn() {
            console.log(this);

        }
        window.fn();
        window.setTimeout(function() {
            console.log(this);

        }, 1000);
        // 2. 方法调用中谁调用this指向谁
        var o = {
            sayHi: function() {
                console.log(this); // this指向的是 o 这个对象

            }
        }
        o.sayHi();
        var btn = document.querySelector('button');
        // btn.onclick = function() {
        //     console.log(this); // this指向的是btn这个按钮对象

        // }
        btn.addEventListener('click', function() {
                console.log(this); // this指向的是btn这个按钮对象

            })
            // 3. 构造函数中this指向构造函数的实例
        function Fun() {
            console.log(this); // this 指向的是fun 实例对象

        }
        var fun = new Fun();
    </script>
</body>

```

### JS执行机制

#### JS是单线程

JavaScript 语言的一大特点就是单线程，也就是说，同一个时间只能做一件事。这是因为 Javascript 这门脚本语言诞生的使命所致——JavaScript 是为处理页面中用户的交互，以及操作 DOM 而诞生的。比如我们对某个 DOM 元素进行添加和删除操作，不能同时进行。 应该先进行添加，之后再删除。
单线程就意味着，所有任务需要排队，前一个任务结束，才会执行后一个任务。这样所导致的问题是： 如果 JS 执行的时间过长，这样就会造成页面的渲染不连贯，导致页面渲染加载阻塞的感觉。

#### 一个问题

以下代码执行的结果是什么？

```js
console.log(1);
setTimeout(function() {
    console.log(3);
},1000);
console.log(2);
```

```js
那么以下代码执行的结果又是什么？

console.log(1);
setTimeout(function() {
    console.log(3);
},0);
console.log(2);
```

#### 同步和异步

- 为了解决这个问题，利用多核 CPU 的计算能力，HTML5 提出 Web Worker 标准，允许 JavaScript 脚本创建多个线程
- 于是，JS 中出现了同步和异步。
- 同步:
-   前一个任务结束后再执行后一个任务
- 异步：
-   在做这件事的同时，你还可以去处理其他事情
- 
- 同步任务
- 
- 同步任务都在主线程上执行，形成一个 执行栈
- 
- 异步任务
- 
- JS中的异步是通过回调函数实现的
- 异步任务有以下三种类型
-  普通事件，如click,resize等
-  资源加载，如load,error等
-  定时器，包括setInterval,setTimeout等
- 异步任务相关回调函数添加到任务队列中- 
![](https://img-blog.csdnimg.cn/f0cc815b48574ce2bb068501a9394a5e.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L0F1Z2Vuc3Rlcm5fUVhM,size_16,color_FFFFFF,t_70#pic_center)

- 先执行执行栈中的同步任务
- 异步任务(回调函数)放入任务队列中
- 一旦执行栈中的所有同步任务执行完毕，系统就会按次序读取任务队列中的异步任务，于是被读取的异步任务结束等待状态，进执行栈，开始执行

![](https://img-blog.csdnimg.cn/d337ebf7ba2c40c7a768fd91f6bfbf56.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L0F1Z2Vuc3Rlcm5fUVhM,size_16,color_FFFFFF,t_70#pic_center)

此时再来看我们刚才的问题：

```js
console.log(1);
setTimeout(function() {
    console.log(3);
},1000);
console.log(2);
```




执行的结果和顺序为 1、2、3

```js
console.log(1);
setTimeout(function() {
    console.log(3);
},0);
console.log(2);
```


执行的结果和顺序为 1、2、3

```js
// 3. 第三个问题
console.log(1);
document.onclick = function() {
    console.log('click');
}
console.log(2);
setTimeout(function() {
    console.log(3)
}, 3000)
```

![](https://img-blog.csdnimg.cn/eaabe7880146428fb68e6e64f23db40c.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L0F1Z2Vuc3Rlcm5fUVhM,size_16,color_FFFFFF,t_70#pic_center)

同步任务放在执行栈中执行，异步任务由异步进程处理放到任务队列中，执行栈中的任务执行完毕会去任务队列中查看是否有异步任务执行，由于主线程不断的重复获得任务、执行任务、再获取任务、再执行，所以这种机制被称为事件循环（ event loop）。

### location对象

window 对象给我们提供了一个 `location`属性用于获取或者设置窗体的url，并且可以解析url。因为这个属性返回的是一个对象，所以我们将这个属性也称为 location 对象。

#### url

==统一资源定位符（uniform resouce locator）==是互联网上标准资源的地址。互联网上的每个文件都有一个唯一的 URL，它包含的信息指出文件的位置以及浏览器应该怎么处理它。

url 的一般语法格式为：

```url
protocol://host[:port]/path/[?query]#fragment

http://www.itcast.cn/index.html?name=andy&age=18#link
```

| 组成     | 说明                                     |
| -------- | ---------------------------------------- |
| protocol | 通信协议 常用的http,ftp,maito等          |
| host     | 主机(域名) www.itheima.com               |
| port     | 端口号，可选                             |
| path     | 路径 由零或多个`'/'`符号隔开的字符串     |
| query    | 参数 以键值对的形式，通过`&`符号分隔开来 |
| fragment | 片段 `#`后面内容 常见于链接 锚点         |

#### location对象属性

| location对象属性  | 返回值                            |
| ----------------- | --------------------------------- |
| location.href     | 获取或者设置整个URL               |
| location.host     | 返回主机（域名）www.baidu.com     |
| location.port     | 返回端口号，如果未写返回空字符串  |
| location.pathname | 返回路径                          |
| location.search   | 返回参数                          |
| location.hash     | 返回片段 #后面内容常见于链接 锚点 |

重点记住： `href`和`search`

需求：5s之后跳转页面

```html
<body>
    <button>点击</button>
    <div></div>
    <script>
        var btn = document.querySelector('button');
        var div = document.querySelector('div');
        var timer = 5;
        setInterval(function() {
            if (timer == 0) {
                location.href = 'http://www.itcast.cn';
            } else {
                div.innerHTML = '您将在' + timer + '秒钟之后跳转到首页';
                timer--;
            }

        }, 1000);
    </script>
</body>

```

#### location对象方法

| location对象方法   | 返回值                                                       |
| ------------------ | ------------------------------------------------------------ |
| location.assign()  | 跟href一样，可以跳转页面（也称为重定向页面）                 |
| location.replace() | 替换当前页面，因为不记录历史，所以不能后退页面               |
| location.reload()  | 重新加载页面，相当于刷新按钮或者 f5 ，如果参数为true 强制刷新 ctrl+f5 |

#### 获取URL参数

我们简单写一个登录框，点击登录跳转到 index.html

```html
<body>
    <form action="index.html">
        用户名： <input type="text" name="uname">
        <input type="submit" value="登录">
    </form>
</body>

```

接下来我们写 index.html

```html
<body>
    <div></div>
    <script>
        console.log(location.search); // ?uname=andy
        // 1.先去掉？  substr('起始的位置'，截取几个字符);
        var params = location.search.substr(1); // uname=andy
        console.log(params);
        // 2. 利用=把字符串分割为数组 split('=');
        var arr = params.split('=');
        console.log(arr); // ["uname", "ANDY"]
        var div = document.querySelector('div');
        // 3.把数据写入div中
        div.innerHTML = arr[1] + '欢迎您';
    </script>
</body>
```

这样我们就能获取到路径上的URL参数

#### navigator对象

- navigator 对象包含有关浏览器的信息，它有很多属性
- 我们常用的是`userAgent`,该属性可以返回由客户机发送服务器的`user-agent`头部的值

下面前端代码可以判断用户是用哪个终端打开页面的，如果是用 PC 打开的，我们就跳转到 PC 端的页面，如果是用手机打开的，就跳转到手机端页面

```js
if((navigator.userAgent.match(/(phone|pad|pod|iPhone|iPod|ios|iPad|Android|Mobile|BlackBerry|IEMobile|MQQBrowser|JUC|Fennec|wOSBrowser|BrowserNG|WebOS|Symbian|Windows Phone)/i))) {
    window.location.href = "";     //手机
 } else {
    window.location.href = "";     //电脑
 }
```

#### history对象

- window 对象给我们提供了一个 history 对象，与浏览器历史记录进行交互
- 该对象包含用户（在浏览器窗口中）访问过的 URL。

| history对象方法 | 作用                                                         |
| --------------- | ------------------------------------------------------------ |
| back()          | 可以后退功能                                                 |
| forward()       | 前进功能                                                     |
| go(参数)        | 前进后退功能，参数如果是 1 前进1个页面 如果是 -1 后退1个页面 |

```html
<body>
    <a href="list.html">点击我去往列表页</a>
    <button>前进</button>
    <script>
        var btn = document.querySelector('button');
        btn.addEventListener('click', function() {
            // history.forward();
            history.go(1);
        })
    </script>
</body>
```

### PC端网页特效

### offset 概述

offset 即偏移量，使用 offset 系列相关属性可以 **动态的** 获取该元素的位置（偏移）、大小等，如：

- 元素距离带有定位父元素的位置
- 获取元素自身的大小（宽度高度）

注：返回的数值不带单位

offset 系列常用的属性包括：

**element.offsetParent**

返回作为该元素带有定位的父级元素，如果父级元素没有定位，则返回 body

注意，parentNode 和 offsetParent 还是有本质上的区别的：parentNode 返回的是直接父级元素，offsetParent 返回的是带有定位的父级元素。
**element.offsetTop**

返回元素带有定位父元素上方的偏移

**element.offsetLeft**

返回元素带有定位父元素左边框的偏移

**element.offsetWidth**

返回自身包括 padding, 边框, 内容区的宽度，返回数值不带单位

**element.offsetHeight**

返回自身包括 padding, 边框, 内容区的高度，返回数值不带单位

#### offset 和 style 的区别

| offset                                             | style                                                    |
| -------------------------------------------------- | -------------------------------------------------------- |
| offset 可以得到任意样式表中的样式值                | style 只能得到行内样式表中的样式值，无法获得内嵌样式     |
| offset 系列获得的数值是没有单位的                  | `style.width` 获得的是带有单位的字符串                   |
| offsetWidth 包含 padding+border+width              | `style.width` 获得不包含 padding 和 border 的值          |
| offsetWidth 等属性是只读属性，只能获取不能赋值     | style 属性是可读写属性，`style.width` 可以获取也可以赋值 |
| **只想要获取元素大小位置的时候，用 offset 更合适** | **要对元素样式进行修改的话，使用 style 更合适**          |

##### offset 学习案例

获得鼠标在盒子中的坐标

拖曳窗口

仿京东放大镜

### cilent

![image-20220308175648877](C:\Users\87160\AppData\Roaming\Typora\typora-user-images\image-20220308175648877.png)

### scroll

![img](https://img-blog.csdnimg.cn/20200413194016375.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MzM5MjQ4OQ==,size_16,color_FFFFFF,t_70)

![img](https://img-blog.csdnimg.cn/20200413194603288.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MzM5MjQ4OQ==,size_16,color_FFFFFF,t_70)



### 三大系列总结

![image-20220308182804088](C:\Users\87160\AppData\Roaming\Typora\typora-user-images\image-20220308182804088.png)

![image-20220308182909265](C:\Users\87160\AppData\Roaming\Typora\typora-user-images\image-20220308182909265.png)





### 立即执行函数

立即执行函数模式是一种语法，可以让你的函数在定义后立即被执行。

立即执行函数只有一个作用！！!

就是创建一个独立[作用域](https://so.csdn.net/so/search?q=作用域&spm=1001.2101.3001.7020)  这个作用域里面的变量  外面是访问不到的

下面是经典面试题可以帮助您更好的理解

![](https://img-blog.csdnimg.cn/20200812173506254.png)

![img](https://img-blog.csdnimg.cn/20200812173517603.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NTc2NjAzNA==,size_16,color_FFFFFF,t_70)

因为 JS 中调用函数传递参数都是值传递 ，所以当立即执行函数执行时，首先会把参数 i 的值复制一份，然后再创建函数作用域来执行函数，循环5次就会创建5个作用域，所以每个 li 元素访问的都是不同作用域的 i 的值 。

立即执行函数的作用和闭包一样 都是 减少全局变量的使用

立即执行函数只是一种函数执行方式 

就是在函数声明完立即执行 

这类函数一般只执行一次

调用完结束后会立即销毁

不会占用内存


#### 立即执行函数的组成

- 定义一个函数
- 将整个函数包裹在一对括号中
   将函数声明转换为表达式
- 在结尾加上一对括号
   让函数立即被执行

##### 代码实例

```js
(function () {
    console.log("app")
})()
```

##### 作用 

页面加载完成后只执行一次的设置函数。

将设置函数中的变量包裹在局部作用域中，不会泄露成全局变量。
代码实例1

```js
(function (who) {
    console.log("I miss you, " + who)
})("kangkang")
```

代码实例2

```js
(function (global) {
    console.log(global)
})(this)
```

通常，全局变量被作为一个参数传递给立即执行参数，这样它在函数内部不使用window也可以被访问到。

##### 注意

通常你不应该给立即执行函数传递太多的参数，因为它很快会成为一个负担——为了理解代码是如何工作的，你不得不经常上下滚动源代码。

##### 返回值

就像其它任何函数一样，一个立即执行函数也能返回值并且可以赋值给其它变量。

```js
var num = (function () {
    return 4
})()
console.log(num)
```



### 三种前端本地存储方式讲解

#### **cookie**

##### **前言**

网络早期最大的问题之一是如何管理状态。简而言之，服务器无法知道两个请求是否来自同一个浏览器。当时最简单的方法是在请求时，在页面中插入一些参数，并在下一个请求中传回参数。这需要使用包含参数的隐藏的表单，或者作为URL参数的一部分传递。这两个解决方案都手动操作，容易出错。cookie出现来解决这个问题。

##### **作用**

cookie是纯文本，没有可执行代码。存储数据，当用户访问了某个网站（网页）的时候，我们就可以通过cookie来向访问者电脑上存储数据，或者某些网站为了辨别用户身份、进行session跟踪而储存在用户本地终端上的数据（通常经过加密）

##### **如何工作**

当网页要发http请求时，浏览器会先检查是否有相应的cookie，有则自动添加在request header中的cookie字段中。这些是浏览器自动帮我们做的，而且每一次http请求浏览器都会自动帮我们做。这个特点很重要，因为这关系到“什么样的数据适合存储在cookie中”。

存储在cookie中的数据，每次都会被浏览器自动放在http请求中，如果这些数据并不是每个请求都需要发给服务端的数据，浏览器这设置自动处理无疑增加了网络开销；但如果这些数据是每个请求都需要发给服务端的数据（比如身份认证信息），浏览器这设置自动处理就大大免去了重复添加操作。所以对于那种设置“每次请求都要携带的信息（最典型的就是身份认证信息）”就特别适合放在cookie中，其他类型的数据就不适合了。

##### **特征**

1. 不同的浏览器存放的cookie位置不一样，也是不能通用的。
2. cookie的存储是以域名形式进行区分的，不同的域下存储的cookie是独立的。
3. 我们可以设置cookie生效的域（当前设置cookie所在域的子域），也就是说，我们能够操作的cookie是当前域以及当前域下的所有子域
4. 一个域名下存放的cookie的个数是有限制的，不同的浏览器存放的个数不一样,一般为20个。
5. 每个cookie存放的内容大小也是有限制的，不同的浏览器存放大小不一样，一般为4KB。
6. cookie也可以设置过期的时间，默认是会话结束的时候，当时间到期自动销毁

cookie值既可以设置，也可以读取

##### **设置**

**客户端设置**

```
  document.cookie = '名字=值';document.cookie = 'username=cfangxu;domain=baike.baidu.com'    并且设置了生效域
```

注意：客户端可以设置cookie 的下列选项：expires、domain、path、secure（有条件：只有在https协议的网页中，客户端设置secure类型的 cookie 才能成功），但无法设置HttpOnly选项。

**服务器端设置**

不管你是请求一个资源文件（如 html/js/css/图片），还是发送一个ajax请求，服务端都会返回response。而response header中有一项叫set-cookie，是服务端专门用来设置cookie的。

Set-Cookie 消息头是一个字符串，其格式如下（中括号中的部分是可选的）：

```
  Set-Cookie: value[; expires=date][; domain=domain][; path=path][; secure]
```

注意：一个set-Cookie字段只能设置一个cookie，当你要想设置多个 cookie，需要添加同样多的set-Cookie字段。

服务端可以设置cookie 的所有选项：expires、domain、path、secure、HttpOnly

通过 Set-Cookie 指定的这些可选项只会在浏览器端使用，而不会被发送至服务器端。

##### **读取**

我们通过document.cookie来获取当前网站下的cookie的时候，得到的字符串形式的值，它包含了当前网站下所有的cookie（为避免跨域脚本(xss)攻击，这个方法只能获取非 HttpOnly 类型的cookie）。它会把所有的cookie通过一个分号+空格的形式串联起来，例如 `username=chenfangxu;job=coding`

##### **修改 cookie**

要想修改一个cookie，只需要重新赋值就行，旧的值会被新的值覆盖。但要注意一点，在设置新cookie时，path/domain这几个选项一定要旧cookie 保持一样。否则不会修改旧值，而是添加了一个新的 cookie。

##### **删除**

把要删除的cookie的过期时间设置成已过去的时间,path/domain/这几个选项一定要旧cookie 保持一样。

##### **注意**

如果只设置一个值，那么算cookie中的value; 设置的两个cookie,key值如果设置的相同，下面的也会把上面的覆盖。

##### **cookie的属性（可选项）**

**过期时间**

如果我们想长时间存放一个cookie。需要在设置这个cookie的时候同时给他设置一个过期的时间。如果不设置，cookie默认是临时存储的，当浏览器关闭进程的时候自动销毁。

注意：document.cookie = '名称=值;expires=' + GMT(格林威治时间)格式的日期型字符串;

一般设置天数： `newDate().setDate(oDate.getDate()+5);`比当前时间多5天

一个设置cookie时效性的例子：

```
  function setCookie(c_name, value, expiredays){    var exdate=new Date();    exdate.setDate(exdate.getDate() + expiredays);    document.cookie=c_name+ "=" + escape(value) + ((expiredays==null) ? "" : ";expires="+exdate.toGMTString())}
```

使用方法：

```
  setCookie('username','cfangxu',30)
```

> expires 是 http/1.0协议中的选项，在新的http/1.1协议中expires已经由 max-age 选项代替，两者的作用都是限制cookie 的有效时间。expires的值是一个时间点（cookie失效时刻= expires），而max-age 的值是一个以秒为单位时间段（cookie失效时刻= 创建时刻+ max-age）。

另外，max-age 的默认值是 -1(即有效期为 session )；max-age有三种可能值：负数、0、正数。

- 负数：有效期session；
- 0：删除cookie；
- 正数：有效期为创建时刻+ max-age

##### **cookie的域概念（domain选项）**

domain指定了 cookie 将要被发送至哪个或哪些域中。默认情况下，domain 会被设置为创建该 cookie 的页面所在的域名，所以当给相同域名发送请求时该 cookie 会被发送至服务器。

浏览器会把 domain 的值与请求的域名做一个尾部比较（即从字符串的尾部开始比较），并将匹配的 cookie 发送至服务器。

**客户端设置**

```
  document.cookie = "username=cfangxu;path=/;domain=qq.com"
```

如上：“www.qq.com" 与 "sports.qq.com" 公用一个关联的域名"qq.com"，我们如果想让 "sports.qq.com" 下的cookie被 "www.qq.com" 访问，我们就需要用到 cookie 的domain属性，并且需要把path属性设置为 "/"。

**服务端设置**

```
  Set-Cookie: username=cfangxu;path=/;domain=qq.com
```

注：一定的是同域之间的访问，不能把domain的值设置成非主域的域名。

##### **cookie的路径概念（path选项）**

cookie 一般都是由于用户访问页面而被创建的，可是并不是只有在创建 cookie 的页面才可以访问这个 cookie。 因为安全方面的考虑,默认情况下，只有与创建 cookie 的页面在同一个目录或子目录下的网页才可以访问。即path属性可以为服务器特定文档指定cookie，这个属性设置的url且带有这个前缀的url路径都是有效的。

**客户端设置**

最常用的例子就是让 cookie 在根目录下,这样不管是哪个子页面创建的 cookie，所有的页面都可以访问到了。

```
  `document.cookie = "username=cfangxu; path=/"` 
```

**服务端设置**

```
  `Set-Cookie:name=cfangxu; path=/blog`  
```

如上设置：path 选项值会与 /blog，/blogrool 等等相匹配；任何以 /blog 开头的选项都是合法的。需要注意的是，只有在 domain 选项核实完毕之后才会对 path 属性进行比较。path 属性的默认值是发送 Set-Cookie 消息头所对应的 URL 中的 path 部分。

**domain和path总结**

domain是域名，path是路径，两者加起来就构成了 URL，domain和path一起来限制 cookie 能被哪些 URL 访问。

所以domain和path2个选项共同决定了cookie何时被浏览器自动添加到请求头部中发送出去。如果没有设置这两个选项，则会使用默认值。domain的默认值为设置该cookie的网页所在的域名，path默认值为设置该cookie的网页所在的目录。

##### **cookie的安全性（secure选项）**

通常 cookie 信息都是使用HTTP连接传递数据，这种传递方式很容易被查看，所以 cookie 存储的信息容易被窃取。假如 cookie 中所传递的内容比较重要，那么就要求使用加密的数据传输。

secure选项用来设置cookie只在确保安全的请求中才会发送。当请求是HTTPS或者其他安全协议时，包含 secure 选项的 cookie 才能被发送至服务器。

```
  document.cookie = "username=cfangxu; secure" 
```

把cookie设置为secure，只保证 cookie 与服务器之间的数据传输过程加密，而保存在本地的 cookie文件并不加密。就算设置了secure 属性也并不代表他人不能看到你机器本地保存的 cookie 信息。机密且敏感的信息绝不应该在 cookie 中存储或传输，因为 cookie 的整个机制原本都是不安全的。

注意：如果想在客户端即网页中通过 js 去设置secure类型的 cookie，必须保证网页是https协议的。在http协议的网页中是无法设置secure类型cookie的。

##### **httpOnly**

这个选项用来设置cookie是否能通过 js 去访问。默认情况下，cookie不会带httpOnly选项(即为空)，所以默认情况下，客户端是可以通过js代码去访问（包括读取、修改、删除等）这个cookie的。当cookie带httpOnly选项时，客户端则无法通过js代码去访问（包括读取、修改、删除等）这个cookie。

**在客户端是不能通过js代码去设置一个httpOnly类型的cookie的，这种类型的cookie只能通过服务端来设置。**

##### **cookie的编码**

cookie其实是个字符串，但这个字符串中等号、分号、空格被当做了特殊符号。所以当cookie的 key 和 value 中含有这3个特殊字符时，需要对其进行额外编码，一般会用escape进行编码，读取时用unescape进行解码；当然也可以用encodeURIComponent/decodeURIComponent或者encodeURI/decodeURI，查看关于编码的介绍

##### **第三方cookie**

通常cookie的域和浏览器地址的域匹配，这被称为第一方cookie。那么第三方cookie就是cookie的域和地址栏中的域不匹配，这种cookie通常被用在第三方广告网站。为了跟踪用户的浏览记录，并且根据收集的用户的浏览习惯，给用户推送相关的广告。

关于第三方cookie和cookie的安全问题可以查看[https://mp.weixin.qq.com/s/oOGIuJCplPVW3BuIx9tNQg](https://mp.weixin.qq.com/s?__biz=MzU0OTExNzYwNg==&mid=2247484049&idx=1&sn=7817b2ff4906ea80e8cff00d60bbf83f&scene=21#wechat_redirect)

##### **cookie推荐资源**

- 聊一聊 cookie
- HTTP cookies 详解

#### **localStorage（本地存储）**

HTML5新方法，不过**IE8及以上**浏览器都兼容。

##### **特点**

- 生命周期：持久化的本地存储，除非主动删除数据，否则数据是永远不会过期的。
- 存储的信息在同一域中是共享的。
- 当本页操作（新增、修改、删除）了localStorage的时候，本页面不会触发storage事件,但是别的页面会触发storage事件。
- 大小：据说是5M（跟浏览器厂商有关系）
- 在非IE下的浏览中可以本地打开。IE浏览器要在服务器中打开。
- localStorage本质上是对字符串的读取，如果存储内容多的话会消耗内存空间，会导致页面变卡
- localStorage受同源策略的限制

##### **设置**

```
  localStorage.setItem('username','cfangxu');
```

##### **获取**

```
  localStorage.getItem('username')
```

也可以获取键名

```
  localStorage.key(0) #获取第一个键名 
```

##### **删除**

```
  localStorage.remove('username')
```

也可以一次性清除所有存储

```
  localStorage.clear()
```

##### **storage事件**

当storage发生改变的时候触发。

注意：当前页面对storage的操作会触发其他页面的storage事件。

事件的回调函数中有一个参数event,是一个StorageEvent对象，提供了一些实用的属性,如下表：

| Property | Type   | Description                                                  |
| :------- | :----- | :----------------------------------------------------------- |
| key      | String | The named key that was added, removed, or moddified          |
| oldValue | Any    | The previous value(now overwritten), or null if a new item was added |
| newValue | Any    | The new value, or null if an item was added                  |
| url/uri  | String | The page that called the method that triggered this change   |

#### **sessionStorage**

其实跟localStorage差不多，也是本地存储，会话本地存储

##### **特点：**

用于本地存储一个会话（session）中的数据，这些数据只有在同一个会话中的页面才能访问并且当会话结束后数据也随之销毁。因此sessionStorage不是一种持久化的本地存储，仅仅是会话级别的存储。也就是说只要这个浏览器窗口没有关闭，即使刷新页面或进入同源另一页面，数据仍然存在。关闭窗口后，sessionStorage即被销毁，或者在新窗口打开同源的另一个页面，sessionStorage也是没有的。

#### **cookie、localStorage、sessionStorage区别**

相同：在本地（浏览器端）存储数据。

不同：

- localStorage、sessionStorage
- localStorage只要在相同的协议、相同的主机名、相同的端口下，就能读取/修改到同一份localStorage数据。
- sessionStorage比localStorage更严苛一点，除了协议、主机名、端口外，还要求在同一窗口（也就是浏览器的标签页）下。
- localStorage是永久存储，除非手动删除。
- sessionStorage当会话结束（当前页面关闭的时候，自动销毁）
- cookie的数据会在每一次发送http请求的时候，同时发送给服务器而localStorage、sessionStorage不会。

## 方法大全

### insertAdjacentHTML

**`insertAdjacentHTML()`** 方法将指定的文本解析为 [`Element`](https://developer.mozilla.org/zh-CN/docs/Web/API/Element) 元素，并将结果节点插入到DOM树中的指定位置。它不会重新解析它正在使用的元素，因此它不会破坏元素内的现有元素。这避免了额外的序列化步骤，使其比直接使用innerHTML操作更快。

#### [语法](https://developer.mozilla.org/zh-CN/docs/Web/API/Element/insertAdjacentHTML#语法)

```
element.insertAdjacentHTML(position, text);
```

- `position`

  一个 [`DOMString`](https://developer.mozilla.org/zh-CN/docs/Web/API/DOMString)，表示插入内容相对于元素的位置，并且必须是以下字符串之一：   `'beforebegin'`：元素自身的前面。  `'afterbegin'`：插入元素内部的第一个子节点之前。  `'beforeend'`：插入元素内部的最后一个子节点之后。  `'afterend'`：元素自身的后面。  

- `text`

  是要被解析为HTML或XML元素，并插入到DOM树中的 [`DOMString`](https://developer.mozilla.org/zh-CN/docs/Web/API/DOMString)。

##### 双击事件ondblclick

##### remove（）；

##### click（）；

##### select（）；文本框里面的文字处于选中状态

### AJAX

https://blog.csdn.net/weixin_44972008/article/details/113772348

### AJAX概述

#### AJAX简介

AJAX 全称为Asynchronous JavaScript And [XML](https://so.csdn.net/so/search?q=XML&spm=1001.2101.3001.7020)，就是异步的JS 和XML
 通过AJAX 可以在浏览器中向服务器发送异步请求，最大的优势：**无刷新获取数据**
 AJAX 不是新的编程语言，而是一种将现有的标准组合在一起使用的新方式

#### XML 简介

XML 可扩展标记语言。
XML 被设计用来传输和存储数据。
XML 和HTML 类似，不同的是HTML 中都是预定义标签，而XML 中没有预定义标签，
全都是自定义标签，用来表示一些数据。

比如说我有一个学生数据：
name = “孙悟空” ; age = 18 ; gender = “男” ;
用XML 表示：

```xml
<student>
	<name>孙悟空</name>
	<age>18</age>
	<gender>男</gender>
</student>
```

现在已经被JSON 取代了。

```json
{"name":"孙悟空","age":18,"gender":"男"}
```

#### AJAX 的特点

##### AJAX 的优点

1. 可以无需刷新页面而与服务器端进行通信
2. 允许你根据用户事件来更新部分页面内容

##### 1.3.2 AJAX 的缺点

1. 没有浏览历史，不能回退
2. 存在跨域问题(同源)
3. SEO 不友好

### HTTP相关问题

#### MDN 文档

https://developer.mozilla.org/zh-CN/docs/Web/HTTP/Overview

#### HTTP 请求交互的基本过程

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210302161144256.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDk3MjAwOA==,size_16,color_FFFFFF,t_70)

1. 前后应用从浏览器端向服务器发送HTTP 请求(请求报文)
2. 后台服务器接收到请求后, 调度服务器应用处理请求, 向浏览器端返回HTTP响应(响应报文)
3. 浏览器端接收到响应, 解析显示响应体/调用监视回调

#### HTTP 请求报文

1. 请求行

method url
GET /product_detail?id=2
POST /login

2. 多个请求头

Host: www.baidu.com
Cookie: BAIDUID=AD3B0FA706E; BIDUPSID=AD3B0FA706;
Content-Type: application/x-www-form-urlencoded 或者application/json
3. 请求体

username=tom&pwd=123
{"username": "tom", "pwd": 123}

#### HTTP 响应报文

1. 响应状态行: `status statusText`
2. 多个响应头
    `Content-Type: text/html;charset=utf-8`
    `Set-Cookie: BD_CK_SAM=1;path=/`
3. 响应体
    `html 文本/json 文本/js/css/图片...`

#### post 请求体参数格式

1：Content-Type: application/x-www-form-urlencoded;charset=utf-8
用于键值对参数，参数的键值用=连接, 参数之间用&连接
例如: name=%E5%B0%8F%E6%98%8E&age=12
2：Content-Type: application/json;charset=utf-8
用于 json 字符串参数
例如: {"name": "%E5%B0%8F%E6%98%8E", "age": 12}
3：Content-Type: multipart/form-data
用于文件上传请求

#### 常见的响应状态码

200 OK 请求成功。一般用于GET 与POST 请求
201 Created 已创建。成功请求并创建了新的资源
401 Unauthorized 未授权/请求要求用户的身份认证
404 Not Found 服务器无法根据客户端的请求找到资源
500 Internal Server Error 服务器内部错误，无法完成请求

#### 不同类型的请求及其作用

1. `GET`: 从服务器端**读取**数据（查）
2. `POST`: 向服务器端**添加**新数据 （增）
3. `PUT`: **更新**服务器端已经数据 （改）
4. `DELETE`: **删除**服务器端数据 （删）

#### API 的分类

REST API: restful （Representational State Transfer (资源)表现层状态转化）
(1) 发送请求进行CRUD 哪个操作由请求方式来决定
(2) 同一个请求路径可以进行多个操作
(3) 请求方式会用到GET/POST/PUT/DELETE
非REST API: restless
(1) 请求方式不决定请求的CRUD 操作
(2) 一个请求路径只对应一个操作
(3) 一般只有GET/POST

#### 区别 一般http请求 与 ajax请求

ajax请求 是一种特别的 http请求
对服务器端来说, 没有任何区别, 区别在浏览器端
浏览器端发请求: 只有XHR 或fetch 发出的才是ajax 请求, 其它所有的都是非ajax 请求
浏览器端接收到响应
(1) 一般请求: 浏览器一般会直接显示响应体数据, 也就是我们常说的刷新/跳转页面
(2) ajax请求: 浏览器不会对界面进行任何更新操作, 只是调用监视的回调函数并传入响应相关数据

### 原生AJAX 的基本使用 XHR

#### 安装node.js

http://nodejs.cn/

#### 安装express（服务端框架）

https://www.expressjs.com.cn/

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210209164615378.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDk3MjAwOA==,size_16,color_FFFFFF,t_70)



1. 初始化环境

```shell
npm init --yes
```

   2.下载express包

```shell
npm install express --save
```

   3.编写js代码

```js
// 1. 引入express
const express = require('express');

// 2. 创建应用对象
const app = express();

// 3. 创建路由规则
// request 是对请求报文的封装
// response 是对响应报文的封装
app.get('/', (request, response) => {
  //  设置响应
  response.send("Hello Express");
});

// 4. 监听端口，启动服务
app.listen(8000, () => {
  console.log("服务已经启动, 8000 端口监听中...");
 })


```

4.运行js程序

```shell
node .\01express使用.js
```

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210209165304650.png)

5.打开网页显示页面

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210209165339872.png)



6.调试程序可以查看请求和响应



![在这里插入图片描述](https://img-blog.csdnimg.cn/2021020916541663.png)



![在这里插入图片描述](https://img-blog.csdnimg.cn/20210209165526228.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDk3MjAwOA==,size_16,color_FFFFFF,t_70)





#### 安装nodemon自动重启工具

文件内容有修改自动重新启动服务
 https://www.npmjs.com/package/nodemon

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210301205043799.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDk3MjAwOA==,size_16,color_FFFFFF,t_70)



安装

```powershell
npm install -g nodemon
```

启动服务

```powershell
ndoemon server.js
```

### 理解

1. 使用`XMLHttpRequest` (XHR)对象可以与服务器交互, 也就是发送ajax 请求
2. 前端可以获取到数据，而无需让整个的页面刷新。
3. 这使得Web 页面可以只更新页面的局部，而不影响用户的操作。

https://developer.mozilla.org/zh-CN/docs/Web/API/XMLHttpRequest
 `XMLHttpRequest`，AJAX 的所有操作都是通过该对象进行的

### 核心对象使用步骤

#### 创建XMLHttpRequest 对象

```javascript
const xhr = new XMLHttpRequest();
```

#### 设置请求信息（请求方法和url）

```js
// 请求方式
xhr.open(method, url);
//可以设置请求头，一般不设置
xhr.setRequestHeader('Content-Type', 'application/x-www-form-urlencoded');
```

#### 发送请求

```javascript
xhr.send(body) //get请求不传 body 参数，只有post请求使用
```

####  接收响应（事件绑定，处理服务端返回的结果）

```js
//xhr.responseXML 接收 xml格式 的响应数据
//xhr.responseText 接收 文本格式 的响应数据
xhr.onreadystatechange = function (){
	// readyState 是 xhr对象中的属性, 表示状态 0 1 2 3 4
	if(xhr.readyState == 4 && xhr.status == 200){
		var text = xhr.responseText;
		console.log(text);
	}
}
```



### 使用案例

1：GET 请求

2：POST请求

3：json数据请求

4：请求超时与网络异常

5：取消请求

6：请求重复发送问题

7：解决 IE 缓存问题

#### AJAX 请求状态

`xhr.readyState` 可以用来查看请求当前的状态
 https://developer.mozilla.org/zh-CN/docs/Web/API/XMLHttpRequest/readyState

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210218121704846.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDk3MjAwOA==,size_16,color_FFFFFF,t_70)

0: 表示XMLHttpRequest 实例已经生成，但是open()方法还没有被调用
1: 表示send()方法还没有被调用，仍然可以使用setRequestHeader()，设定HTTP请求的头信息
2: 表示send()方法已经执行，并且头信息和状态码已经收到
3: 表示正在接收服务器传来的body 部分的数据
4: 表示服务器数据已经完全接收，或者本次接收已经失败了

### API总结

1. XMLHttpRequest()：创建 XHR 对象的构造函数
2. status：响应状态码值，如 200、404
3. statusText：响应状态文本，如 ’ok‘、‘not found’
4. readyState：标识请求状态的只读属性 0-1-2-3-4
5. onreadystatechange：绑定 readyState 改变的监听
6. responseType：指定响应数据类型，如果是 ‘json’，得到响应后自动解析响应
7. response：响应体数据，类型取决于 responseType 的指定
8. timeout：指定请求超时时间，默认为 0 代表没有限制
9. ontimeout：绑定超时的监听
10. onerror：绑定请求网络错误的监听
11. open()：初始化一个请求，参数为：(method, url[, async])
12. send(data)：发送请求
13. abort()：中断请求 （发出到返回之间）
14. getResponseHeader(name)：获取指定名称的响应头值
15. getAllResponseHeaders()：获取所有响应头组成的字符串
16. setRequestHeader(name, value)：设置请求头

### 跨域

#### 同源策略

- 同源策略(Same-Origin Policy)最早由Netscape 公司提出，是浏览器的一种安全策略
- 同源： 协议、域名、端口号必须完全相同
- 跨域： 违背同源策略就是**跨域**

#### 如何解决跨域

##### JSONP

1) JSONP 是什么

JSONP(JSON with Padding)，是一个非官方的跨域解决方案，纯粹凭借程序员的聪明
才智开发出来，只支持get 请求。
2) JSONP 怎么工作的？

在网页有一些标签天生具有跨域能力，比如：img link iframe script。
JSONP 就是利用script 标签的跨域能力来发送请求的。
3) JSONP 的使用
1.动态的创建一个script 标签

```js
var script = document.createElement("script");
```

​        2.设置script 的src，设置回调函数

```js
script.src = "http://localhost:3000/testAJAX?callback=abc";
function abc(data) {
	alert(data.name);
};
```

​         3.将script 添加到body 中

```js
document.body.appendChild(script);
```

​        4.服务器中路由的处理

```js
router.get("/testAJAX" , function (req , res) {
	console.log("收到请求");
	var callback = req.query.callback;
	var obj = {
		name:"孙悟空",
		age:18
	}
	res.send(callback+"("+JSON.stringify(obj)+")");
});
```

##### CORS

https://developer.mozilla.org/zh-CN/docs/Web/HTTP/Access_control_CORS

#### 1）CORS 是什么？

CORS（Cross-Origin Resource Sharing），跨域资源共享。CORS 是官方的跨域解决方
案，它的特点是不需要在客户端做任何特殊的操作，完全在服务器中进行处理，支持
get 和post 请求。跨域资源共享标准新增了一组HTTP 首部字段，允许服务器声明哪些
源站通过浏览器有权限访问哪些资源

#### 2) CORS 怎么工作的？

CORS 是通过设置一个响应头来告诉浏览器，该请求允许跨域，浏览器收到该响应
 以后就会对响应放行。

#### 3) CORS 的使用

主要是服务器端的设置：

```js
router.get("/testAJAX" , function (req , res) {
	//通过res 来设置响应头，来允许跨域请求
	//res.set("Access-Control-Allow-Origin","http://127.0.0.1:3000");
	res.set("Access-Control-Allow-Origin","*");
	res.send("testAJAX 返回的响应");
});
```



##                                                                                                                           ES6

### 面向对象

面向对象更贴近我们的实际生活, 可以使用面向对象描述现实世界事物. 但是事物分为具体的事物和抽象的事物

面向对象的思维特点：

1. 抽取（抽象）对象共用的属性和行为组织(封装)成一个类(模板)
2. 对类进行实例化, 获取类的对象

### 对象

在 JavaScript 中，对象是一组无序的相关属性和方法的集合，所有的事物都是对象，例如[字符串](https://so.csdn.net/so/search?q=字符串&spm=1001.2101.3001.7020)、数值、数组、函数等。

对象是由属性和方法组成的

- 属性：事物的**特征，\**在对象中用\**属性**来表示
- 方法：事物的**行为，\**在对象中用\**方法**来表示

### 类

在 ES6 中新增加了类的概念，可以使用 class 关键字声明一个类，之后以这个类来实例化对象。

- 类抽象了对象的公共部分，它泛指某一大类（class）
- 对象特指某一个，通过类实例化一个具体的对象

#### 创建类

```JS
class name {
    // class body
}
```

#### 创建实例

```JS
var XX = new name();
```

注意：类必须使用`new` 实例化对象

#### 构造函数

constructor() 方法是类的构造函数(默认方法)，用于传递参数,返回实例对象，通过 new 命令生成对象实例时，自动调用该方法。如果没有显示定义, 类内部会自动给我们创建一个constructor()

```HTML
<script>
    // 1. 创建类 class  创建一个 明星类
    class Star {
        // constructor 构造器或者构造函数
        constructor(uname, age) {
            this.uname = uname;
            this.age = age;
        }
    }

    // 2. 利用类创建对象 new
    var ldh = new Star('刘德华', 18);
    var zxy = new Star('张学友', 20);
    console.log(ldh);
    console.log(zxy);
</script>

```

通过 class 关键字创建类，类名我们还是习惯性**定义首字母大写**

类里面有个 `constructor`函数，可以接收传递过来的参数，同时返回实例对象

`constructor`函数只要 new 生成实例时，就会自动调用这个函数，如果我们不写这个函数，类也会自动生成这个函数

最后注意语法规范   

- 创建类➡类名后面不要加小括号
- 生成实例➡类名后面加小括号
- 构造函数不需要加 function 关键字

#### 类中添加方法

```JS
class Person {
  constructor(name,age) {   
      // constructor 称为构造器或者构造函数
      this.name = name;
      this.age = age;
    }
   say() {
      console.log(this.name + '你好');
   }
}      
var ldh = new Person('刘德华', 18); 
ldh.say() 
```

**注意**： 方法之间不能加逗号分隔，同时方法不需要添加 function 关键字。

```HTML
<script>
    // 1. 创建类 class  创建一个 明星类
    class Star {
        // 类的共有属性放到 constructor 里面
        constructor(uname, age) {
            this.uname = uname;
            this.age = age;
        }
        sing(song) {
            console.log(this.uname + song);
        }
    }

    // 2. 利用类创建对象 new
    var ldh = new Star('刘德华', 18);
    var zxy = new Star('张学友', 20);
    console.log(ldh);
    console.log(zxy);
    // (1) 我们类里面所有的函数不需要写function 
    // (2) 多个函数方法之间不需要添加逗号分隔
    ldh.sing('冰雨');
    zxy.sing('李香兰');
</script>

```

- 类的共有属性放到`constructor` 里面
- 类里面的函数都不需要写 `function` 关键字

### 类的继承

现实中的继承：子承父业，比如我们都继承了父亲的姓。

程序中的继承：子类可以继承父类的一些属性和方法。

语法：

```JS
// 父类
class Father {
    
}
// 子类继承父类
class Son extends Father {
    
}
```

看一个实例

```html
<script>
    // 父类有加法方法
    class Father {
        constructor(x, y) {
            this.x = x;
            this.y = y;
        }
        sum() {
            console.log(this.x + this.y);
        }
    }
    // 子类继承父类加法方法 同时 扩展减法方法
    class Son extends Father {
        constructor(x, y) {
            // 利用super 调用父类的构造函数
            // super 必须在子类this之前调用
            super(x, y);
            this.x = x;
            this.y = y;
        }
        subtract() {
            console.log(this.x - this.y);
        }
    }
    var son = new Son(5, 3);
    son.subtract();
    son.sum();
</script>
```

#### super关键字

- `super` 关键字用于访问和调用对象父类上的函数，可以调用父类的构造函数，也可以调用父类的普通函数

#### 子类对父类方法的重写

```html
<script>
    class Phone{
        constructor(brand,price) {
            this.brand=brand;
            this.price=price;

        }
        //父类的成员属性
        call(){
            console.log('我可以打电话')
        }
    }
    class SmartPhone extends Phone{
        constructor(brand,price,color,size) {
            super(brand,price);
            this.color=color;
            this.size=size;
        }
        photo(){
            console.log('拍照');
        }

        playGame(){
            console.log('打游戏');
        }

        //重写！
        call(){
            console.log('我可以进行视频通话')//这里不能用super()
        }
    }
    const xiaomi=new SmartPhone('小米',1999,'黑色','4.7inch')
    xiaomi.call();
    xiaomi.photo();
    xiaomi.playGame();
</script>
```



#### 调用父类的构造函数

```js
// 父类
class Person {
    constructor(surname){
        this.surname = surname;
    }
}
// 子类继承父类
class Student entends Person {
    constructor(surname,firstname) {
        super(surname);					//调用父类的 constructor(surname)
        this.firstname = firstname;		//定义子类独有的属性
    }
}
```

注意：**子类在构造函数中使用super,必须放到this前面（必须先调用父类的构造方法，再使用子类构造方法）**

#### 调用父类的普通函数

```js
class Father {	
    say() {
        return '我是爸爸';
    }
}
class Son extends Father {
    say(){
        // super.say() super调用父类的方法
        return super.say() + '的儿子';
    }
}

var damao = new Son();
console.log(damao.say());
```

- 多个方法之间不需要添加逗号分隔
- 继承中属性和方法的查找原则：就近原则，先看子类，再看父类

#### getter和setter

```js
  class Phone{
        get price(){
            console.log('价格属性被读取');
            return 'iloveu'
        }
        set price(value){
            console.log('价格属性被修改了');
        }
    }
    let p=new Phone();
    console.log(p.price);//价格属性被读取 /n iloveu
    p.price='free';//价格属性被修改了
```



### 三个注意点

1. 在ES6中类没有变量提升，所以必须先定义类，才能通过类实例化对象
2. 类里面的共有属性和方法一定要加 `this`使用
3. 类里面的this指向：   
   - constructor 里面的 `this`指向实例对象
   - 方法里面的`this`指向这个方法的调用者

```html
<body>
    <button>点击</button>
    <script>
        var that;
        var _that;
        class Star {
            constructor(uname, age) {
                // constructor 里面的this 指向的是 创建的实例对象
                that = this;
                this.uname = uname;
                this.age = age;
                // this.sing();
                this.btn = document.querySelector('button');
                this.btn.onclick = this.sing;
            }
            sing() {
            // 这个sing方法里面的this 指向的是 btn 这个按钮,因为这个按钮调用了这个函数
                console.log(that.uname); 
                // that里面存储的是constructor里面的this
            }
            dance() {
                // 这个dance里面的this 指向的是实例对象 ldh 因为ldh 调用了这个函数
                _that = this;
                console.log(this);
            }
        }
        var ldh = new Star('刘德华');
        console.log(that === ldh);
        ldh.dance();
        console.log(_that === ldh);

        // 1. 在 ES6 中类没有变量提升，所以必须先定义类，才能通过类实例化对象

        // 2. 类里面的共有的属性和方法一定要加this使用.
    </script>
</body>

```

### 构造函数和原型

#### 概述

在典型的 OOP 的语言中（如 Java），都存在类的概念，类就是对象的模板，对象就是类的实例，但在 ES6之前， JS 中并没用引入类的概念。

ES6， 全称 ECMAScript 6.0 ，2015.06 发版。但是目前浏览器的 JavaScript 是 ES5 版本，大多数高版本的浏览器也支持 ES6，不过只实现了 ES6 的部分特性和功能。

在 ES6之前 ，对象不是基于类创建的，而是用一种称为构建函数的特殊函数来定义对象和它们的特征。

创建对象有三种方式
    对象字面量
    new Object()
    自定义构造函数

```js
// 1. 利用 new Object() 创建对象
var obj1 = new Object();

// 2. 利用对象字面量创建对象
var obj2 = {}；

// 3.利用构造函数创建对象
function Star(uname,age) {
    this.uname = uname;
    this.age = age;
    this.sing = function() {
        console.log('我会唱歌');
    }
}
var ldh = new Star('刘德华',18);

```

注意：

1. 构造函数用于创建某一类对象，其首字母要大写
2. 构造函数要和`new`一起使用才有意义

#### 构造函数

- 构造函数是一种特殊的函数，主要用来初始化对象(为对象成员变量赋初始值)，它总与new一起使用
- 我们可以把对象中的一些公共的属性和方法抽取出来，然后封装到这个函数里面

new 在执行时会做四件事

- 在内存中创建一个新的空对象。
- 让 this 指向这个新的对象。
- 执行构造函数里面的代码，给这个新对象添加属性和方法。
- 返回这个新对象（所以构造函数里面不需要 return ）。
##### 静态成员和实例成员

JavaScript 的构造函数中可以添加一些成员，可以在构造函数本身上添加，也可以在构造函数内部的`this`上添加。通过这两种方式添加的成员，就分别称为静态成员和实例成员。**（类里面则是在属性和方法前面加上 static）**

- 静态成员: 在构造函数本身上添加的成员为静态成员，只能由构造函数本身来访问
- 实例成员: 在构造函数内部创建的对象成员称为实例成员，只能由实例化的对象来访问

```js
// 构造函数中的属性和方法我们称为成员，成员可以添加
function Star(uname,age) {
    this.uname = uname;
    this.age = age;
    this.sing = function() {
        console.log('我会唱歌');
    }
}
var ldh = new Star('刘德华',18);

// 实例成员就是构造函数内部通过this添加的成员  uname age sing  就是实例成员
// 实例成员只能通过实例化的对象来访问
ldh.sing();
Star.uname; // undefined     不可以通过构造函数来访问实例成员

// 静态成员就是在构造函数本身上添加的成员 sex 就是静态成员
// 静态成员只能通过构造函数来访问
Star.sex = '男';
Star.sex;
ldh.sex; // undefined  不能通过对象来访问

```











#### 构造函数的问题

构造函数方法很好用，但是存在浪费内存的问题。

![在这里插入图片描述](https://img-blog.csdnimg.cn/080f8513ab074159abf16942fd009b2b.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L0F1Z2Vuc3Rlcm5fUVhM,size_16,color_FFFFFF,t_70#pic_center)

**我们希望所有的对象使用同一个函数，这样就比较节省内存**

#### 构造函数原型 prototype

构造函数通过原型分配的函数是所有对象所共享的,这样就解决了内存浪费问题
JavaScript 规定，每一个构造函数都有一个prototype属性，指向另一个对象，注意这个prototype就是一个对象，这个对象的所有属性和方法，都会被构造函数所拥有
我们可以把那些不变的方法，直接定义在prototype 对象上，这样所有对象的实例就可以共享这些方法

```html
<body>
    <script>
        // 1. 构造函数的问题. 
        function Star(uname, age) {
    		//公共属性定义到构造函数里面
            this.uname = uname;
            this.age = age;
            // this.sing = function() {
            //     console.log('我会唱歌');
            // }
        }
		//公共的方法我们放到原型对象身上
        Star.prototype.sing = function() {
            console.log('我会唱歌');
        }
        var ldh = new Star('刘德华', 18);
        var zxy = new Star('张学友', 19);
        console.log(ldh.sing === zxy.sing);
        ldh.sing();
        zxy.sing();
        // 2. 一般情况下,我们的公共属性定义到构造函数里面, 公共的方法我们放到原型对象身上
    </script>
</body>

```

一般情况下,我们的公共属性定义到构造函数里面, 公共的方法我们放到原型对象身上

问答：原型是什么？

- 一个对象，我们也称为 `prototype` 为原型对象

问答：原型的作用是什么？

- 共享方法

#### 对象原型 __ proto __

对象都会有一个属性 _proto_ 指向构造函数的prototype原型对象，之所以我们对象可以使用构造函数prototype 原型对象的属性和方法，就是因为对象有_proto_原型的存在。
_proto_对象原型和原型对象 prototype 是等价的
_proto_对象原型的意义就在于为对象的查找机制提供一个方向，或者说一条路线，但是它是一个非标准属性，因此实际开发中，不可以使用这个属性，它只是内部指向原型对象 prototype
![在这里插入图片描述](https://img-blog.csdnimg.cn/e8e771c189c548f7b67209722f6289dc.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L0F1Z2Vuc3Rlcm5fUVhM,size_16,color_FFFFFF,t_70#pic_center)

`Star.prototype 和 ldh._proto_` 指向相同

```html
<body>
    <script>
        function Star(uname, age) {
            this.uname = uname;
            this.age = age;
        }
        Star.prototype.sing = function() {
            console.log('我会唱歌');
        }
        var ldh = new Star('刘德华', 18);
        var zxy = new Star('张学友', 19);
        ldh.sing();
        console.log(ldh); 
		// 对象身上系统自己添加一个 __proto__ 指向我们构造函数的原型对象 prototype
        console.log(ldh.__proto__ === Star.prototype);
        // 方法的查找规则: 首先先看ldh 对象身上是否有 sing 方法,如果有就执行这个对象上的sing
        // 如果没有sing 这个方法,因为有 __proto__ 的存在,就去构造函数原型对象prototype身上去查找sing这个方法
    </script>
</body>

```

#### constructor 构造函数

对象原型(__ proto __) 和构造函数(prototype)原型对象 里面都有一个属性 constructor 属性， constructor 我们称为构造函数，因为它指回构造函数本身。

constructor主要用于记录该对象引用于哪个构造函数，它可以让原型对象重新指向原来的构造函数
一般情况下，对象的方法都在构造函数(prototype)的原型对象中设置如果有多个对象的方法，我们可以给原型对象prototype采取对象形式赋值，但是这样会覆盖构造函数原型对象原来的内容，这样修改后的原型对象constructor就不再指向当前构造函数了。此时，我们可以在修改后的原型对象中，添加一个constructor指向原来的构造函数

```html
<body>
    <script>
        function Star(uname, age) {
            this.uname = uname;
            this.age = age;
        }
        // 很多情况下,我们需要手动的利用constructor 这个属性指回 原来的构造函数
        // Star.prototype.sing = function() {
        //     console.log('我会唱歌');
        // };
        // Star.prototype.movie = function() {
        //     console.log('我会演电影');
        // }
        Star.prototype = {
            // 如果我们修改了原来的原型对象,给原型对象赋值的是一个对象,则必须手动的利用constructor指回原来的构造函数
            constructor: Star,
            sing: function() {
                console.log('我会唱歌');
            },
            movie: function() {
                console.log('我会演电影');
            }
        }
        var ldh = new Star('刘德华', 18);
        var zxy = new Star('张学友', 19);
    </script>
</body>

```

#### 构造函数、实例、原型对象三者关系

![在这里插入图片描述](https://img-blog.csdnimg.cn/8ee8345e99974afd93ce053e7988712d.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L0F1Z2Vuc3Rlcm5fUVhM,size_16,color_FFFFFF,t_70#pic_center)

#### 原型链查找规则

当访问一个对象的属性(包括方法)时，首先查找这个对象自身有没有该属性
如果没有就查找它的原型(也就是_proto_指向的prototype原型对象)
如果还没有就查找原型对象的原型(Object的原型对象)
依次类推一直找到Object为止(null)
__ proto __对象原型的意义就在于为对象成员查找机制提供一个方向，或者说一条路线。
![在这里插入图片描述](https://img-blog.csdnimg.cn/c1cbd18ff3444621bf151654714b85cd.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L0F1Z2Vuc3Rlcm5fUVhM,size_16,color_FFFFFF,t_70#pic_center)



```html
<body>
    <script>
        function Star(uname, age) {
            this.uname = uname;
            this.age = age;
        }
        Star.prototype.sing = function() {
            console.log('我会唱歌');
        }
        var ldh = new Star('刘德华', 18);
        // 1. 只要是对象就有__proto__ 原型, 指向原型对象
        console.log(Star.prototype);
        console.log(Star.prototype.__proto__ === Object.prototype);
        // 2.我们Star原型对象里面的__proto__原型指向的是 Object.prototype
        console.log(Object.prototype.__proto__);
        // 3. 我们Object.prototype原型对象里面的__proto__原型  指向为 null
    </script>
</body>

```

#### 原型对象this指向

- 构造函数中的 `this`指向我们的实例对象
- 原型对象里面放的是方法，这个方法里面的`this`指向的是这个方法的调用者，也就是这个实例对象

```html
<body>
    <script>
        function Star(uname, age) {
            this.uname = uname;
            this.age = age;
        }
        var that;
        Star.prototype.sing = function() {
            console.log('我会唱歌');
            that = this;
        }
        var ldh = new Star('刘德华', 18);
        // 1. 在构造函数中,里面this指向的是对象实例 ldh
        ldh.sing();
        console.log(that === ldh);

        // 2.原型对象函数里面的this 指向的是 实例对象 ldh
    </script>
</body>

```

#### 扩展内置对象

- 可以通过原型对象，对原来的内置对象进行扩展自定义的方法
- 比如给数组增加自定义求偶数和的功能

```html
<body>
    <script>
        // 原型对象的应用 扩展内置对象方法

        Array.prototype.sum = function() {
            var sum = 0;
            for (var i = 0; i < this.length; i++) {
                sum += this[i];
            }
            return sum;
        };
        // Array.prototype = {
        //     sum: function() {
        //         var sum = 0;
        //         for (var i = 0; i < this.length; i++) {
        //             sum += this[i];
        //         }
        //         return sum;
        //     }

        // }
        var arr = [1, 2, 3];
        console.log(arr.sum());
        console.log(Array.prototype);
        var arr1 = new Array(11, 22, 33);
        console.log(arr1.sum());
    </script>
</body>

```

注意：

- 数组和字符串内置对象不能给原型对象覆盖操作`Array.prototype = {}`，只能是`Array.prototype.xxx = function(){}`的方式

### 继承

ES6 之前并没有给我们提供`extends`继承

- 我们可以通过构造函数+原型对象模拟实现继承，被称为组合继承

#### call()

调用这个函数，并且修改函数运行时的 this 指向

```js
fun.call(thisArg,arg1,arg2,......)
```

- `thisArg`：当前调用函数 this 的指向对象
- `arg1,arg2`： 传递的其他参数

```html
<body>
    <script>
        // call 方法
        function fn(x, y) {
            console.log('我希望我的希望有希望');
            console.log(this);		// Object{...}
            console.log(x + y);		// 3
        }

        var o = {
            name: 'andy'
        };
        // fn();
        // 1. call() 可以调用函数
        // fn.call();
        // 2. call() 可以改变这个函数的this指向 此时这个函数的this 就指向了o这个对象
        fn.call(o, 1, 2);
    </script>
</body>

```

#### 借用构造函数继承父类型属性

核心原理: 通过 `call()` 把父类型的 this 指向子类型的 this，这样就可以实现子类型继承父类型的属性

```html
<body>
    <script>
        // 借用父构造函数继承属性
        // 1. 父构造函数
        function Father(uname, age) {
            // this 指向父构造函数的对象实例
            this.uname = uname;
            this.age = age;
        }
        // 2 .子构造函数 
        function Son(uname, age, score) {
            // this 指向子构造函数的对象实例
            Father.call(this, uname, age);
            this.score = score;
        }
        var son = new Son('刘德华', 18, 100);
        console.log(son);
    </script>
</body>
```

#### 借用原型对象继承父类型方法

核心原理：

1. 将子类所共享的方法提取出来，让子类的 `prototype 原型对象 = new 父类()`
2. 本质： 子类原型对象等于是实例化父类，因为父类实例化之后另外开辟空间，就不会影响原来父类原型对象
3. 将子类的`constructor`重新指向子类的构造函数

```html
<body>
    <script>
        // 借用父构造函数继承属性
        // 1. 父构造函数
        function Father(uname, age) {
            // this 指向父构造函数的对象实例
            this.uname = uname;
            this.age = age;
        }
        Father.prototype.money = function() {
            console.log(100000);

        };
        // 2 .子构造函数 
        function Son(uname, age, score) {
            // this 指向子构造函数的对象实例
            Father.call(this, uname, age);
            this.score = score;
        }
        // Son.prototype = Father.prototype;  这样直接赋值会有问题,如果修改了子原型对象,父原型对象也会跟着一起变化
        Son.prototype = new Father();
        // 如果利用对象的形式修改了原型对象,别忘了利用constructor 指回原来的构造函数
        Son.prototype.constructor = Son;
        // 这个是子构造函数专门的方法
        Son.prototype.exam = function() {
            console.log('孩子要考试');

        }
        var son = new Son('刘德华', 18, 100);
        console.log(son);
        console.log(Father.prototype);
        console.log(Son.prototype.constructor);
    </script>
</body>

```

#### 类的本质

class 本质还是 function
类的所有方法都定义在类的 prototype属性上
类创建的实例，里面也有_proto_指向类的prototype原型对象
所以 ES6 的类它的绝大部分功能，ES5都可以做到，新的class写法只是让对象原型的写法更加清晰、更像面向对象编程的语法而已。
所以 ES6 的类其实就是语法糖
语法糖：语法糖就是一种便捷写法，简单理解

### ES5新增方法

ES5 给我们新增了一些方法，可以很方便的操作数组或者字符串

- 数组方法
- 字符串方法
- 对象方法

#### 数组方法

迭代(遍历)方法：foreach() ，map()，filter()，some() ，every() ;

##### forEach()

```js
array.forEach(function(currentValue,index,arr))
```

- currentValue : 数组当前项的值
- index: 数组当前项的索引
- arr: 数组对象本身

```html
<body>
    <script>
        // forEach 迭代(遍历) 数组
        var arr = [1, 2, 3];
        var sum = 0;
        arr.forEach(function(value, index, array) {
            console.log('每个数组元素' + value);
            console.log('每个数组元素的索引号' + index);
            console.log('数组本身' + array);
            sum += value;
        })
        console.log(sum);
    </script>
</body>
```

##### filter()筛选数组

- `filter()`方法创建一个新的数组，新数组中的元素是通过检查指定数组中符合条件的所有元素，主要用于筛选数组
  - 注意它直接返回一个新数组

##### some()

- `some()`方法用于检测数组中的元素是否满足指定条件（查找数组中是否有满足条件的元素）
- 注意它返回的是布尔值，如果查找到这个元素，就返回true，如果查找不到就返回false
- 如果找到第一个满足条件的元素，则终止循环，不再继续查找

#### Array.prototype.reduce()

**`reduce()`** 方法对数组中的每个元素按序执行一个由您提供的 **reducer** 函数，每一次运行 **reducer** 会将先前元素的计算结果作为参数传入，最后将其结果汇总为单个返回值。

第一次执行回调函数时，不存在“上一次的计算结果”。如果需要回调函数从数组索引为 0 的元素开始执行，则需要传递初始值。否则，数组索引为 0 的元素将被作为初始值 *initialValue*，迭代器将从第二个元素开始执行（索引为 1 而不是 0）。

下面的例子能够帮助你理解 `reduce()` 的用处——计算数组所有元素的总和：

```js
const array1 = [1, 2, 3, 4];

// 0 + 1 + 2 + 3 + 4
const initialValue = 0;
const sumWithInitial = array1.reduce(
  (previousValue, currentValue) => previousValue + currentValue,
  initialValue
);

console.log(sumWithInitial);
// expected output: 10
```



#### 字符串方法

- `trim()`方法会从一个字符串的两端删除空白字符
- `trim()`方法并不影响原字符串本身，它返回的是一个新的字符串 

#### 对象方法

##### Object.keys()

1. `Object.keys()`用于获取对象自身所有的属性
2. 效果类似`for...in`
3. 返回一个由属性名组成的数组

```HTML
<body>
    <script>
        // 用于获取对象自身所有的属性
        var obj = {
            id: 1,
            pname: '小米',
            price: 1999,
            num: 2000
        };
        var arr = Object.keys(obj);
        console.log(arr);
        arr.forEach(function(value) {
            console.log(value);
            // id
            // pname
            // price
            // num
        })
    </script>
</body>

```

##### Object.defineProperty()

`Object.defineProperty()`定义对象中新属性或修改原有的属性(了解)

```js
Object.defineProperty(obj,prop,descriptor)
```

- obj : 目标对象
- prop : 需定义或修改的属性的名字
- descriptor : 目标属性所拥有的特性

```html
<body>
    <script>
        // Object.defineProperty() 定义新属性或修改原有的属性
        var obj = {
            id: 1,
            pname: '小米',
            price: 1999
        };
        // 1. 以前的对象添加和修改属性的方式
        // obj.num = 1000;
        // obj.price = 99;
        // console.log(obj);
        // 2. Object.defineProperty() 定义新属性或修改原有的属性
        Object.defineProperty(obj, 'num', {
            value: 1000,
            enumerable: true
        });
        console.log(obj);
        Object.defineProperty(obj, 'price', {
            value: 9.9
        });
        console.log(obj);
        Object.defineProperty(obj, 'id', {
            // 如果值为false 不允许修改这个属性值 默认值也是false
            writable: false,
        });
        obj.id = 2;
        console.log(obj);
        Object.defineProperty(obj, 'address', {
            value: '中国山东蓝翔技校xx单元',
            // 如果只为false 不允许修改这个属性值 默认值也是false
            writable: false,
            // enumerable 如果值为false 则不允许遍历, 默认的值是 false
            enumerable: false,
            // configurable 如果为false 则不允许删除这个属性 不允许在修改第三个参数里面的特性 默认为false
            configurable: false
        });
        console.log(obj);
        console.log(Object.keys(obj));
        delete obj.address;
        console.log(obj);
        delete obj.pname;
        console.log(obj);
        Object.defineProperty(obj, 'address', {
            value: '中国山东蓝翔技校xx单元',
            // 如果值为false 不允许修改这个属性值 默认值也是false
            writable: true,
            // enumerable 如果值为false 则不允许遍历, 默认的值是 false
            enumerable: true,
            // configurable 如果为false 则不允许删除这个属性 默认为false
            configurable: true
        });
        console.log(obj.address);
    </script>
</body>

```

第三个参数 descriptor 说明：以对象形式{ }书写
value：设置属性的值，默认为undefined
writeable: 值是否可以重写 true | false 默认为false
enumerable: 目标属性是否可以被枚举 true | false 默认为false
configurable: 目标属性是否可以被删除或是否可以再次修改特性 true | false 默认为false

### 函数进阶

#### 函数的定义方式

1. 函数声明方式 function 关键字(命名函数)
2. 函数表达式(匿名函数)
3. new Function()

```js
var fn = new Function('参数1','参数2',.....,'函数体');
```

- Function 里面参数都必须是字符串格式
- 第三种方式执行效率低，也不方便书写，因此较少使用
- 所有函数都是 Function 的实例(对象)
- 函数也属于对象

![在这里插入图片描述](https://img-blog.csdnimg.cn/41f3e6248b384edba0cef92f7557b9b3.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L0F1Z2Vuc3Rlcm5fUVhM,size_16,color_FFFFFF,t_70#pic_center)

#### 函数的调用方式


​        // 函数的调用方式

```js
    // 1. 普通函数
    function fn() {
        console.log('人生的巅峰');

    }
    // fn();   fn.call()
    // 2. 对象的方法
    var o = {
        sayHi: function() {
            console.log('人生的巅峰');

        }
    }
    o.sayHi();
    // 3. 构造函数
    function Star() {};
    new Star();
    // 4. 绑定事件函数
    // btn.onclick = function() {};   // 点击了按钮就可以调用这个函数
    // 5. 定时器函数
    // setInterval(function() {}, 1000);  这个函数是定时器自动1秒钟调用一次
    // 6. 立即执行函数
    (function() {
        console.log('人生的巅峰');
    })();
    // 立即执行函数是自动调用

```
#### 函数内this的指向

`this`指向，是当我们调用函数的时候确定的，调用方式的不同决定了`this`的指向不同，一般我们指向我们的调用者

| 调用方式     | this指向                                   |
| ------------ | ------------------------------------------ |
| 普通函数调用 | window                                     |
| 构造函数调用 | 实例对象，原型对象里面的方法也指向实例对象 |
| 对象方法调用 | 该方法所属对象                             |
| 事件绑定方法 | 绑定事件对象                               |
| 定时器函数   | window                                     |
| 立即执行函数 | window                                     |

```html
<body>
    <button>点击</button>
    <script>
        // 函数的不同调用方式决定了this 的指向不同
        // 1. 普通函数 this 指向window
        function fn() {
            console.log('普通函数的this' + this);
        }
        window.fn();
        // 2. 对象的方法 this指向的是对象 o
        var o = {
            sayHi: function() {
                console.log('对象方法的this:' + this);
            }
        }
        o.sayHi();
        // 3. 构造函数 this 指向 ldh 这个实例对象 原型对象里面的this 指向的也是 ldh这个实例对象
        function Star() {};
        Star.prototype.sing = function() {

        }
        var ldh = new Star();
        // 4. 绑定事件函数 this 指向的是函数的调用者 btn这个按钮对象
        var btn = document.querySelector('button');
        btn.onclick = function() {
            console.log('绑定时间函数的this:' + this);
        };
        // 5. 定时器函数 this 指向的也是window
        window.setTimeout(function() {
            console.log('定时器的this:' + this);

        }, 1000);
        // 6. 立即执行函数 this还是指向window
        (function() {
            console.log('立即执行函数的this' + this);
        })();
    </script>
</body>

```

#### 改变函数内部this指向

JavaScript 为我们专门提供了一些函数方法来帮我们处理函数内部 this 的指向问题，常用的有 `bind(),call(),apply()`三种方法

##### call() 方法

call()方法调用一个对象，简单理解为调用函数的方式，但是它可以改变函数的this指向
fun.call(thisArg,arg1,arg2,.....)
thisArg: 在 fun 函数运行时指定的 this 值
arg1,arg2: 传递的其他参数
返回值就是函数的返回值，因为它就是调用函数
**因此当我们想改变 this 指向，同时想调用这个函数的时候，可以使用 call，比如继承**

```html
<body>
    <script>
        // 改变函数内this指向  js提供了三种方法  call()  apply()  bind()

        // 1. call()
        var o = {
            name: 'andy'
        }

        function fn(a, b) {
            console.log(this);
            console.log(a + b);

        };
        fn.call(o, 1, 2);
        // call 第一个可以调用函数 第二个可以改变函数内的this 指向
        // call 的主要作用可以实现继承
        function Father(uname, age, sex) {
            this.uname = uname;
            this.age = age;
            this.sex = sex;
        }

        function Son(uname, age, sex) {
            Father.call(this, uname, age, sex);
        }
        var son = new Son('刘德华', 18, '男');
        console.log(son);
    </script>
</body>

```

##### apply()方法

apply()方法调用一个函数，简单理解为调用函数的方式，但是它可以改变函数的 this指向
fun.apply(thisArg,[argsArray])
thisArg: 在 fun 函数运行时指定的 this 值
argsArray : 传递的值，必须包含在数组里面
返回值就是函数的返回值，因为它就是调用函数
**因此 apply 主要跟数组有关系，比如使用 Math.max() 求数组的最大值**

```html
<body>
    <script>
        // 改变函数内this指向  js提供了三种方法  call()  apply()  bind()

        // 2. apply()  应用 运用的意思
        var o = {
            name: 'andy'
        };

        function fn(arr) {
            console.log(this);
            console.log(arr); // 'pink'

        };
        fn.apply(o, ['pink']);
        // 1. 也是调用函数 第二个可以改变函数内部的this指向
        // 2. 但是他的参数必须是数组(伪数组)
        // 3. apply 的主要应用 比如说我们可以利用 apply 借助于数学内置对象求数组最大值 
        // Math.max();
        var arr = [1, 66, 3, 99, 4];
        var arr1 = ['red', 'pink'];
        // var max = Math.max.apply(null, arr);
        var max = Math.max.apply(Math, arr);
        var min = Math.min.apply(Math, arr);
        console.log(max, min);
    </script>
</body>

```

##### bind()方法

- `bind()`方法不会调用函数。但是能改变函数内部 `this`指向
- `fun.bind(thisArg,arg1,arg2,....)`
- 返回由指定的 `this`值和初始化参数改造的 原函数拷贝
- 因此当我们只是想改变 this 指向，并且不想调用这个函数的时候，可以使用bind

```html
<body>
    <button>点击</button>
    <button>点击</button>
    <button>点击</button>
    <script>
        // 改变函数内this指向  js提供了三种方法  call()  apply()  bind()

        // 3. bind()  绑定 捆绑的意思
        var o = {
            name: 'andy'
        };

        function fn(a, b) {
            console.log(this);
            console.log(a + b);


        };
        var f = fn.bind(o, 1, 2);
        f();
        // 1. 不会调用原来的函数   可以改变原来函数内部的this 指向
        // 2. 返回的是原函数改变this之后产生的新函数
        // 3. 如果有的函数我们不需要立即调用,但是又想改变这个函数内部的this指向此时用bind
        // 4. 我们有一个按钮,当我们点击了之后,就禁用这个按钮,3秒钟之后开启这个按钮
        // var btn1 = document.querySelector('button');
        // btn1.onclick = function() {
        //     this.disabled = true; // 这个this 指向的是 btn 这个按钮
        //     // var that = this;
        //     setTimeout(function() {
        //         // that.disabled = false; // 定时器函数里面的this 指向的是window
        //         this.disabled = false; // 此时定时器函数里面的this 指向的是btn
        //     }.bind(this), 3000); // 这个this 指向的是btn 这个对象
        // }
        var btns = document.querySelectorAll('button');
        for (var i = 0; i < btns.length; i++) {
            btns[i].onclick = function() {
                this.disabled = true;
                setTimeout(function() {
                    this.disabled = false;
                }.bind(this), 2000);
            }
        }
    </script>
</body>

```

#### 总结

call apply bind 总结：

相同点：

- 都可以改变函数内部的 `this`指向

区别点：

- `call`和`apply`会调用函数，并且改变函数内部的`this`指向
- `call`和`apply`传递的参数不一样，call 传递参数，apply 必须数组形式
- `bind`不会调用函数，可以改变函数内部`this`指向

主要应用场景

1. `call`经常做继承
2. `apply`经常跟数组有关系，比如借助于数学对线实现数组最大值与最小值
3. `bind`不调用函数，但是还想改变this指向，比如改变定时器内部的this指向

 ### 严格模式

JavaScript 除了提供正常模式外，还提供了严格模式
ES5 的严格模式是采用具有限制性 JavaScript 变体的一种方式，即在严格的条件下运行 JS 代码
严格模式在IE10 以上版本的浏览器才会被支持，旧版本浏览器会被忽略
严格模式对正常的JavaScript语义做了一些更改：、

​        消除了Javascript 语法的一些不合理、不严谨之处，减少了一些怪异行为
​       消除代码运行的一些不安全之处，保证代码运行的安全
​       提高编译器效率，增加运行速度
​       禁用了在 ECMAScript 的未来版本中可能会定义的一些语法，为未来新版本的 Javascript 做好铺垫。比如一些保留字如：class, enum, 

#### 开启严格模式

- 严格模式可以应用到整个脚本或个别函数中。
- 因此在使用时，我们可以将严格模式分为为脚本开启严格模式和为函数开启严格模式两种情况

##### 为脚本开启严格模式

- 为整个脚本文件开启严格模式，需要在所有语句之前放一个特定语句
- `"use strict"` 或`'use strict'`

```js
<script>
    'user strict';
	console.log("这是严格模式。");
</script>
```

因为"use strict"加了引号，所以老版本的浏览器会把它当作一行普通字符串而忽略。

有的 script 基本是严格模式，有的 script 脚本是正常模式，这样不利于文件合并，所以可以将整个脚本文件放在一个立即执行的匿名函数之中。这样独立创建一个作用域而不影响其他 script 脚本文件。

```html
<script>
	(function (){
    	'use strict';
    	 var num = 10;
    	 function fn() {}
	})();   
</script>
```

##### 为函数开启严格模式

若要给某个函数开启严格模式，需要把`"use strict"`或`'use strict'`声明放在函数体所有语句之前

```html
<body>
    <!-- 为整个脚本(script标签)开启严格模式 -->
    <script>
        'use strict';
        //   下面的js 代码就会按照严格模式执行代码
    </script>
    <script>
        (function() {
            'use strict';
        })();
    </script>
    <!-- 为某个函数开启严格模式 -->
    <script>
        // 此时只是给fn函数开启严格模式
        function fn() {
            'use strict';
            // 下面的代码按照严格模式执行
        }

        function fun() {
            // 里面的还是按照普通模式执行
        }
    </script>
</body>

```

将`"use strict"` 放在函数体的第一行，则整个函数以 "严格模式"运行。

#### 严格模式中的变化

严格模式对JavaScript的语法和行为，都做了一些改变

##### 变量规定

- 在正常模式中，如果一个变量没有声明就赋值，默认是全局变量
- 严格模式禁止这种用法，变量都必须先用var 命令声明，然后再使用
- 严禁删除已经声明变量，例如，``delete x` 语法是错误的

##### 严格模式下this指向问题

1.以前在全局作用域函数中的this指向window对象
2.严格模式下全局作用域中函数中的this 是 undefined
3.以前构造函数时不加 new 也可以调用，当普通函数，this指向全局对象
4.严格模式下，如果构造函数不加 new 调用，this指向的是 undefined ，如果给它赋值，会报错
5.new 实例化的构造函数指向创建的对象实例
6.定时器this 还是指向window
7.事件、对象还是指向调用者

```html
<body>
    <script>
        'use strict';
		//3. 严格模式下全局作用域中函数中的 this 是 undefined。
        function fn() {
            console.log(this); // undefined。

        }
        fn();
        //4. 严格模式下,如果 构造函数不加new调用, this 指向的是undefined 如果给他赋值则 会报错.
        function Star() {
            this.sex = '男';
        }
        // Star();
        var ldh = new Star();
        console.log(ldh.sex);
        //5. 定时器 this 还是指向 window 
        setTimeout(function() {
            console.log(this);

        }, 2000);
        
    </script>
</body>

```

##### 函数变化

1. 函数不能有重名的**参数**
2. 函数必须声明在顶层，新版本的JavaScript会引入“块级作用域”（ES6中已引入）。为了与新版本接轨，**不允许在非函数的代码块内声明函数**

### 高阶函数

- 高阶函数是对其他函数进行操作的函数，它接收函数作为参数或将函数作为返回值输出

接收函数作为参数

```html
<body>
    <div></div>
    <script>
        // 高阶函数- 函数可以作为参数传递
        function fn(a, b, callback) {
            console.log(a + b);
            callback && callback();
        }
        fn(1, 2, function() {
            console.log('我是最后调用的');

        });

    </script>
</body>
```

将函数作为返回值

<script>
    function fn(){
        return function() {}
    }
</script>

```html
<script>
    function fn(){
        return function() {}
    }
</script>
```

- 此时 fn 就是一个高阶函数
- 函数也是一种数据类型，同样可以作为参数，传递给另外一个参数使用。最典型的就是作为回调函数
- 同理函数也可以作为返回值传递回来

### 闭包

#### 变量作用域

变量根据作用域的不同分为两种：全局变量和局部变量

1. 函数内部可以使用全局变量
2. 函数外部不可以使用局部变量
3. 当函数执行完毕，本作用域内的局部变量会销毁。

#### 什么是闭包

闭包指有权访问另一个函数作用域中的变量的函数

简单理解：一个作用域可以访问另外一个函数内部的局部变量

```html
<body>
    <script>
        // 闭包（closure）指有权访问另一个函数作用域中变量的函数。
        // 闭包: 我们fn2 这个函数作用域 访问了另外一个函数 fn1 里面的局部变量 num
        function fn1() {		// fn1就是闭包函数
            var num = 10;
            function fn2() {
                console.log(num); 	//10
            }
            fn2();
        }
        fn1();
    </script>
</body>
```

#### 在chrome中调试闭包

打开浏览器，按 F12 键启动 chrome 调试工具。

设置断点。

找到 Scope 选项（Scope 作用域的意思）。

当我们重新刷新页面，会进入断点调试，Scope 里面会有两个参数（global 全局作用域、local 局部作用域）。

当执行到 fn2() 时，Scope 里面会多一个 Closure 参数 ，这就表明产生了闭包。
![在这里插入图片描述](https://img-blog.csdnimg.cn/487a2da725794758b4e1e2cf54c1aa18.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L0F1Z2Vuc3Rlcm5fUVhM,size_16,color_FFFFFF,t_70#pic_center)

#### 闭包的作用

延伸变量的作用范围

```html
<body>
    <script>
        // 闭包（closure）指有权访问另一个函数作用域中变量的函数。
        // 一个作用域可以访问另外一个函数的局部变量 
        // 我们fn 外面的作用域可以访问fn 内部的局部变量
        // 闭包的主要作用: 延伸了变量的作用范围
        function fn() {
            var num = 10;
            return function() {
                console.log(num);
            }
        }
        var f = fn();
        f();
    </script>
</body>

```

```html
<body>
    <ul class="nav">
        <li>榴莲</li>
        <li>臭豆腐</li>
        <li>鲱鱼罐头</li>
        <li>大猪蹄子</li>
    </ul>
    <script>
        // 闭包应用-点击li输出当前li的索引号
        // 1. 我们可以利用动态添加属性的方式
        var lis = document.querySelector('.nav').querySelectorAll('li');
        for (var i = 0; i < lis.length; i++) {
            lis[i].index = i;
            lis[i].onclick = function() {
                // console.log(i);
                console.log(this.index);

            }
        }
        // 2. 利用闭包的方式得到当前小li 的索引号
        for (var i = 0; i < lis.length; i++) {
            // 利用for循环创建了4个立即执行函数
            // 立即执行函数也成为小闭包因为立即执行函数里面的任何一个函数都可以使用它的i这变量
            (function(i) {
                // console.log(i);
                lis[i].onclick = function() {
                    console.log(i);

                }
            })(i);
        }
    </script>
</body>

```

#### 定时器中的闭包

```html
<body>
    <ul class="nav">
        <li>榴莲</li>
        <li>臭豆腐</li>
        <li>鲱鱼罐头</li>
        <li>大猪蹄子</li>
    </ul>
    <script>
        // 闭包应用-3秒钟之后,打印所有li元素的内容
        var lis = document.querySelector('.nav').querySelectorAll('li');
        for (var i = 0; i < lis.length; i++) {
            (function(i) {
                setTimeout(function() {
                    console.log(lis[i].innerHTML);
                }, 3000)
            })(i);
        }
    </script>
</body>
```

### 递归

**如果一个函数在内部可以调用其本身，那么这个函数就是递归函数**

简单理解： 函数内部自己调用自己，这个函数就是递归函数

由于递归很容易发生"栈溢出"错误，所以必须要加退出条件 return

### 浅拷贝和深拷贝

1. 浅拷贝只是拷贝一层，更深层次对象级别的只拷贝引用
2. 深拷贝拷贝多层，每一级别的数据都会拷贝
3. `Object.assign(target,....sources)` ES6新增方法可以浅拷贝

#### 浅拷贝

```js
// 浅拷贝只是拷贝一层，更深层次对象级别的只拷贝引用
var obj = {
    id: 1,
    name: 'andy',
    msg: {
        age: 18
    }
};
var o = {}
for(var k in obj){
    // k是属性名，obj[k]是属性值
    o[k] = obj.[k];
}
console.log(o);
// 浅拷贝语法糖
Object.assign(o,obj);

```

#### 深拷贝

```js
// 深拷贝拷贝多层，每一级别的数据都会拷贝
var obj = {
    id: 1,
    name: 'andy',
    msg: {
        age: 18
    }
    color: ['pink','red']
};
var o = {};
// 封装函数
function deepCopy(newobj,oldobj){
    for(var k in oldobj){
        // 判断属性值属于简单数据类型还是复杂数据类型
        // 1.获取属性值   oldobj[k]
        var item = obldobj[k];
        // 2.判断这个值是否是数组
        if(item instanceof Array){
            newobj[k] = [];
            deepCopy(newobj[k],item)
        }else if (item instanceof Object){
              // 3.判断这个值是否是对象
            newobj[k] = {};
            deepCopy(newobj[k],item)
        }else {
            // 4.属于简单数据类型
            newobj[k] = item;
            
        } 
    }
}
deepCopy(o,obj);
```

### 数值扩展

1. Number.EPSILON：Number.EPSILON 是 JavaScript 表示的最小精度；EPSILON 属性的值接近于2.2204460492503130808472633361816E-16；

2. 二进制和八进制：ES6 提供了二进制和八进制数值的新的写法，分别用前缀 0b 和 0o 表示；

3. Number.isFinite() 与 Number.isNaN() ：

4. Number.isFinite() 用来检查一个数值是否为有限的；

5. Number.isNaN() 用来检查一个值是否为 NaN；

6. Number.parseInt() 与 Number.parseFloat()：ES6 将全局方法 parseInt 和 parseFloat，移植到 Number 对象上面，使用不变；

7. Math.trunc：用于去除一个数的小数部分，返回整数部分；

8. Number.isInteger：Number.isInteger() 用来判断一个数值是否为整数；

```JS
    // 数值扩展
    // 0. Number.EPSILON 是 JavaScript 表示的最小精度 // EPSILON 属性的值接近于 2.2204460492503130808472633361816E-16
    function equal(a, b) {
        return Math.abs(a - b) < Number.EPSILON;
    }

    console.log("0、Number.EPSILON 是 JavaScript 表示的最小精度");
    // 箭头函数简化写法
    equal = (a, b) => Math.abs(a - b) < Number.EPSILON;
    console.log(0.1 + 0.2);
    console.log(0.1 + 0.2 === 0.3); // false
    console.log(equal(0.1 + 0.2, 0.3)); // true

    // 1. 二进制和八进制
    console.log("1、二进制和八进制");
    let b = 0b1010;
    let o = 0o777;
    let d = 100;
    let x = 0xff;
    console.log(x);

    // 2. Number.isFinite 检测一个数值是否为有限数
    console.log("2、Number.isFinite 检测一个数值是否为有限数");
    console.log(Number.isFinite(100));
    console.log(Number.isFinite(100 / 0));
    console.log(Number.isFinite(Infinity));

    // 3. Number.isNaN 检测一个数值是否为 NaN
    console.log("3. Number.isNaN 检测一个数值是否为 NaN");
    console.log(Number.isNaN(123));

    // 4. Number.parseInt Number.parseFloat字符串转整数
    console.log("4. Number.parseInt Number.parseFloat字符串转整数");
    console.log(Number.parseInt('5211314love'));
    console.log(Number.parseFloat('3.1415926神奇'));

    // 5. Number.isInteger 判断一个数是否为整数
    console.log("5. Number.isInteger 判断一个数是否为整数");
    console.log(Number.isInteger(5));
    console.log(Number.isInteger(2.5));

    // 6. Math.trunc 将数字的小数部分抹掉
    console.log("6. Math.trunc 将数字的小数部分抹掉 ");
    console.log(Math.trunc(3.5));

```



### 对象方法扩展

ES6 新增了一些 Object 对象的方法：

1. Object.is 比较两个值是否严格相等，与『===』行为基本一致（+0 与 NaN）；
2. Object.assign 对象的合并，将源对象的所有可枚举属性，复制到目标对象；
3. proto、setPrototypeOf、 setPrototypeOf 可以直接设置对象的原型；

```JS
    // 对象扩展
    // 1. Object.is 比较两个值是否严格相等，与『===』行为基本一致（+0 与 NaN）；
    console.log(Object.is(120,120)); // ===

    // 注意下面的区别
    console.log(Object.is(NaN,NaN));
    console.log(NaN === NaN); // NaN与任何数值做===比较都是false，跟他自己也如此！

    // 2. Object.assign 对象的合并，将源对象的所有可枚举属性，复制到目标对象；
    const config1 = {
        host: "localhost",
        port: 3306,
        name: "root",
        pass: "root",
        test: "test" // 唯一存在
    }
    const config2 = {
        host: "http://zibo.com",
        port: 300300600,
        name: "root4444",
        pass: "root4444",
        test2: "test2"
    }

    // 如果前边有后边没有会添加，如果前后都有，后面的会覆盖前面的
    console.log(Object.assign(config1,config2));

    // 3. __proto__、setPrototypeOf、 getPrototypeOf 可以直接设置对象的原型；
    const school = {name: "尚硅谷"}
    const cities = {xiaoqu: ['北京', '上海', '深圳']}
    // 并不建议这么做
    Object.setPrototypeOf(school, cities);
    console.log(Object.getPrototypeOf(school));
    console.log(school);

```



### 正则表达式

正则表达式是用于匹配字符串中字符组合的模式。在JavaScript中，正则表达式也是对象。

正则表通常被用来检索、替换那些符合某个模式（规则）的文本，例如验证[表单](https://so.csdn.net/so/search?q=表单&spm=1001.2101.3001.7020)：用户名表单只能输入英文字母、数字或者下划线， 昵称输入框中可以输入中文(匹配)。此外，正则表达式还常用于过滤掉页面内容中的一些敏感词(替换)，或从字符串中获取我们想要的特定部分(提取)等 。

#### 特点

- 实际开发，一般都是直接复制写好的正则表达式
- 但是要求会使用正则表达式并且根据自身实际情况修改正则表达式

#### 创建正则表达式

在JavaScript中，可以通过两种方式创建正则表达式

1. 通过调用 RegExp 对象的构造函数创建
2. 通过字面量创建

##### 通过调用 RegExp 对象的构造函数创建

```js
var 变量名 = new RegExp(/表达式/);
```

##### 通过字面量创建

```js
var 变量名 = /表达式/;
```

#### 测试正则表达式 test

`test()`正则对象方法，用于检测字符串是否符合该规则，该对象会返回`true`或`false`,其参数是测试字符串

```js
regexObj.test(str)
```

- `regexObj` 写的是正则表达式
- `str` 我们要测试的文本
- 就是检测`str`文本是否符合我们写的正则表达式规范

```html
<body>
    <script>
        // 正则表达式在js中的使用

        // 1. 利用 RegExp对象来创建 正则表达式
        var regexp = new RegExp(/123/);
        console.log(regexp);

        // 2. 利用字面量创建 正则表达式
        var rg = /123/;
        // 3.test 方法用来检测字符串是否符合正则表达式要求的规范
        console.log(rg.test(123));
        console.log(rg.test('abc'));
    </script>
</body>

```

### 正则表达式中的特殊字符

#### 边界符

正则表达式中的边界符(位置符)用来提示字符所处的位置，主要有两个字符

| 边界符 | 说明                         |
| ------ | ---------------------------- |
| ^      | 表示匹配行首的文本(以谁开始) |
| $      | 表示匹配行尾的文本(以谁结束) |

如果^ 和 $ 在一起，表示必须是精确匹配

```js
// 边界符 ^ $
var rg = /abc/;   //正则表达式里面不需要加引号，不管是数字型还是字符串型
// /abc/只要包含有abc这个字符串返回的都是true
console.log(rg.test('abc'));
console.log(rg.test('abcd'));
console.log(rg.test('aabcd'));

var reg = /^abc/;
console.log(reg.test('abc'));   //true
console.log(reg.test('abcd'));	// true
console.log(reg.test('aabcd')); // false

var reg1 = /^abc$/
// 以abc开头，以abc结尾，必须是abc

```

#### 字符类

- 字符类表示有一系列字符可供选择，只要匹配其中一个就可以了
- 所有可供选择的字符都放在方括号内

##### ①[] 方括号

```js
/[abc]/.test('andy');     // true
```

后面的字符串只要包含 `abc` 中任意一个字符,都返回`true`

##### ②[-]方括号内部 范围符

```js
/^[a-z]$/.test()
```

方括号内部加上 - 表示范围，这里表示 a - z 26个英文字母都可以

##### ③[^] 方括号内部 取反符 ^

```js
/[^abc]/.test('andy')   // false
```

方括号内部加上 ^ 表示取反，只要包含方括号内的字符，都返回 `false`

注意和边界符 ^ 区别，边界符写到方括号外面

##### ④字符组合

```js
/[a-z1-9]/.test('andy')    // true
```

方括号内部可以使用字符组合，这里表示包含 a 到 z的26个英文字母和1到9的数字都可以

```html
<body>
    <script>
        //var rg = /abc/;  只要包含abc就可以 
        // 字符类: [] 表示有一系列字符可供选择，只要匹配其中一个就可以了
        var rg = /[abc]/; // 只要包含有a 或者 包含有b 或者包含有c 都返回为true
        console.log(rg.test('andy'));
        console.log(rg.test('baby'));
        console.log(rg.test('color'));
        console.log(rg.test('red'));
        var rg1 = /^[abc]$/; // 三选一 只有是a 或者是 b  或者是c 这三个字母才返回 true
        console.log(rg1.test('aa'));
        console.log(rg1.test('a'));
        console.log(rg1.test('b'));
        console.log(rg1.test('c'));
        console.log(rg1.test('abc'));
        console.log('------------------');

        var reg = /^[a-z]$/; // 26个英文字母任何一个字母返回 true  - 表示的是a 到z 的范围  
        console.log(reg.test('a'));
        console.log(reg.test('z'));
        console.log(reg.test(1));
        console.log(reg.test('A'));
        // 字符组合
        var reg1 = /^[a-zA-Z0-9_-]$/; // 26个英文字母(大写和小写都可以)任何一个字母返回 true  
        console.log(reg1.test('a'));
        console.log(reg1.test('B'));
        console.log(reg1.test(8));
        console.log(reg1.test('-'));
        console.log(reg1.test('_'));
        console.log(reg1.test('!'));
        console.log('----------------');
        // 如果中括号里面有^ 表示取反的意思 千万和 我们边界符 ^ 别混淆
        var reg2 = /^[^a-zA-Z0-9_-]$/;
        console.log(reg2.test('a'));
        console.log(reg2.test('B'));
        console.log(reg2.test(8));
        console.log(reg2.test('-'));
        console.log(reg2.test('_'));
        console.log(reg2.test('!'));
    </script>
</body>

```

#### 量词符

量词符用来设定某个模式出现的次数

| 量词  | 说明             |
| ----- | ---------------- |
| *     | 重复零次或更多次 |
| +     | 重复一次或更多次 |
| ?     | 重复零次或一次   |
| {n}   | 重复n次          |
| {n,}  | 重复n次或更多次  |
| {n,m} | 重复n到m次       |

```html
<body>
    <script>
        // 量词符: 用来设定某个模式出现的次数
        // 简单理解: 就是让下面的a这个字符重复多少次
        // var reg = /^a$/;


        //  * 相当于 >= 0 可以出现0次或者很多次 
        // var reg = /^a*$/;
        // console.log(reg.test(''));
        // console.log(reg.test('a'));
        // console.log(reg.test('aaaa'));

        //  + 相当于 >= 1 可以出现1次或者很多次
        // var reg = /^a+$/;
        // console.log(reg.test('')); // false
        // console.log(reg.test('a')); // true
        // console.log(reg.test('aaaa')); // true

        //  ?  相当于 1 || 0
        // var reg = /^a?$/;
        // console.log(reg.test('')); // true
        // console.log(reg.test('a')); // true
        // console.log(reg.test('aaaa')); // false

        //  {3 } 就是重复3次
        // var reg = /^a{3}$/;
        // console.log(reg.test('')); // false
        // console.log(reg.test('a')); // false
        // console.log(reg.test('aaaa')); // false
        // console.log(reg.test('aaa')); // true
        //  {3, }  大于等于3
        var reg = /^a{3,}$/;
        console.log(reg.test('')); // false
        console.log(reg.test('a')); // false
        console.log(reg.test('aaaa')); // true
        console.log(reg.test('aaa')); // true
        //  {3,16}  大于等于3 并且 小于等于16
        var reg = /^a{3,6}$/;
        console.log(reg.test('')); // false
        console.log(reg.test('a')); // false
        console.log(reg.test('aaaa')); // true
        console.log(reg.test('aaa')); // true
        console.log(reg.test('aaaaaaa')); // false
    </script>
</body>

```

#### 括号总结

1. 大括号 量词符 里面面表示重复次数
2. 中括号 字符集合 匹配方括号中的任意字符
3. 小括号 表示优先级

```js
// 中括号 字符集合 匹配方括号中的任意字符
var reg = /^[abc]$/;
// a || b || c
// 大括号 量词符 里面表示重复次数
var reg = /^abc{3}$/;   // 它只是让c 重复3次 abccc
// 小括号 表示优先级
var reg = /^(abc){3}$/;  //它是让 abc 重复3次

```

在线测试正则表达式：https://c.runoob.com/

### 预定义类

预定义类指的是 某些常见模式的简写写法

| 预定类 | 说明                                                         |
| ------ | ------------------------------------------------------------ |
| \d     | 匹配0-9之间的任一数字，相当于[0-9]                           |
| \D     | 匹配所有0-9以外的字符，相当于[ ^ 0-9]                        |
| \w     | 匹配任意的字母、数字和下划线,相当于[A-Za-z0-9_ ]             |
| \W     | 除所有字母、数字、和下划线以外的字符，相当于[ ^A-Za-z0-9_ ]  |
| \s     | 匹配空格（包括换行符，制表符，空格符等），相当于[\t\t\n\v\f] |
| \S     | 匹配非空格的字符，相当于[ ^ \t\r\n\v\f]                      |

#### 表单验证

分析：

1.手机号码: `/^1[3|4|5|7|8][0-9]{9}$/`

2.QQ: `[1-9][0-9]{4,}` (腾讯QQ号从10000开始)

3.昵称是中文: `^[\u4e00-\u9fa5]{2,8}$`

### 正则表达式中的替换

#### replace 替换

`replace()`方法可以实现替换字符串操作，用来替换的参数可以是一个字符串或是一个正则表达式

```js
stringObject.replace(regexp/substr,replacement)
```

1. 第一个参数: 被替换的字符串或者正则表达式
2. 第二个参数：替换为的字符串
3. 返回值是一个替换完毕的新字符串

```js
// 替换 replace
var str = 'andy和red';
var newStr = str.replace('andy','baby');
var newStr = str.replace(/andy/,'baby');
```

#### 正则表达式参数

```js
/表达式/[switch]
```

`switch`按照什么样的模式来匹配，有三种

- `g`: 全局匹配
- `i`:忽略大小写
- `gi`: 全局匹配 + 忽略大小写

### var,let和const区别

#### 1. 不存在变量提升

- var 命令会发生变量提升现象，即变量可以在声明之前使用，值为undefined。
- let 和 const 则没有变量声明提升的功能，必须要先声明才能使用

#### 不允许重复声明

- var命令能重复声明，后者覆盖前者
- let 和 const不允许在相同作用域内，重复声明同一个变量

#### 作用域

- var 的作用域是以函数为界限
- let 和 const 的作用域是块作用域，块级作用域指 { } 内的范围
- var 可以定义全局变量和局部变量，let 和 const 只能定义局部变量
- const 的声明的常量不能被修改，但对于引用类型来说，堆内存中的值是可以被改变的。

#### 变量作为全局属性

定义的变量会作为window对象的属性，let不会

常量定义的引用类型可以修改，如：

```js
  //1.使用常量定义数组
        const arr = [100, 200, 300];
        console.log(arr);

        arr[0] = "hello";
        console.log(arr);   //['hello', 200, 300]

        //2.使用常量来定义对象
        const obj = {
            name: "Jack",
            age: 22,
            no: "001"
        }
        console.log(obj);

        obj.age = 100;
        console.log(obj);   //{name: "Jack", age: 100,  no: "001"}
```

#### 暂时性死区

定义：块级作用域内存在let命令时，所声明的变量就“绑定”这个区域，不再受外部的影响。

```
{
    //let a 之前的区域成为暂时性死区，调用a 会报错
    let a = "hello";
}
```

### Object.freeze

`const` 声明并不会真的保护数据不被改变。 为了确保数据不被改变，JavaScript 提供了一个函数 `Object.freeze`。

任何更改对象的尝试都将被拒绝，如果脚本在严格模式下运行，将抛出错误。

```js
let obj = {
  name:"FreeCodeCamp",
  review:"Awesome"
};
Object.freeze(obj);
obj.review = "bad";
obj.newProp = "Test";
console.log(obj); 
```

### 数组解构

数组解构允许我们按照一一对应的关系从数组中提取值，然后将值赋值给变量

```js
let arr=[1,2,3];
let[a,b,c]=arr;
//多出的为undifined
```

### 对象解构

对象解构允许我们使用变量的名字匹配对象的属性，匹配成功将对象属性的值赋值给变量

```js
let shuaige={name:'赵世伟',age:21};
let{name,age}=shuaige;
console.log(name);
console.log(age);
```

```js
let{name:myname,age:myage}=shuaige;//起别名
```

### 简化对象写法

ES6 允许在大括号里面，直接写入变量和函数，作为对象的属性和方法（在属性名和变量名相同的情况下），这样的书写更加简洁

```js
        let name = 'LiMing'
        let tell = function(){
            console.log('I am LiMing')
        }

        const liMing = {
            name,
            tell,
            sayHi(){
                console.log('hello')
            }
        }

        // 等效于
        // const liMing = {
        //     name: name,
        //     tell: tell,
        //     sayHi: function(){
        //         console.log('hello')
        //     }
        // }

        console.log(liMing)
        liMing.tell()
        liMing.sayHi()
```

### 箭头函数

与function声明的区别：

箭头函数this是静态的。   

- 箭头函数内的this指向上层对象；始终指向函数声明时所在作用域下的this的值，无法被call改变
- 普通函数内的this指向调用其函数的对象

箭头函数不能作为构造函数实例化对象

箭头函数不能使用arguments变量，但是可以使用`....rest` 

```js
        let fn = ()=>{
            console.log(arguments)
        }

        fn(1, 2, 3) // 报错：Uncaught ReferenceError: arguments is not defined
        

        let fn2 = (...rest)=>{
            console.log(...rest)
        }

        fn2('a','b','c') // a b c

```

#### 箭头函数的简写

 当形参有且只有一个的时候，可以省略`()`
 当代码体只有一条语句的时候，可以省略`{}`，此时`return`必须省略，而且语句的执行结果就是函数的返回值

#### 箭头函数的例子

箭头函数适合与this无关的回调，比如定时器setTimeout(()=>{...}, 2000)、数组的方法回调arr.filter((item)=>{...})；
不适合与this有关的回调，比如dom元素的事件回调ad.addEventListener('click', function(){...}、对象内的方法定义{name: 'LiMing', getName: function(){this.name}}

```js
        // 需求-1 点击div 2s后颜色变红
        
        // 获取元素
        let ad = document.getElementById('ad')
        // 绑定事件
        ad.addEventListener('click', function(){
            setTimeout(function(){
                console.log(this) // 定时器里的this指向window
                this.style.background = 'brown' // 报错
            }, 2000)
        })

        //解决方案1
        // ad.addEventListener('click', function(){
        //     // 保存this的值
        //     let _this = this // _this指向ad
        //     setTimeout(function(){
        //         console.log(_this) 
        //         _this.style.background = 'brown'
        //     }, 2000)
        // })

        // 解决方案2
        // ad.addEventListener('click', function(){
        //     setTimeout(()=>{
        //         console.log(this) 
        //         this.style.background = 'brown' // this指向函数声明时所在作用域下this的值 即ad
        //     }, 2000)
        // })

```

```js
        // 需求-2 从数组中返回偶数的元素
        const arr = [1, 6, 9, 10, 100, 25]
        const result = arr.filter(function(item){
            if(item %2 === 0){
                return true
            }else{
                return false
            }
        })

        // 可以用箭头函数
        // const result = arr.filter(item => {
        //     if(item % 2 === 0){
        //         return true
        //     }else{
        //         return false
        //     }
        // })
        // 还可以简写为
        // const result = arr.filter(item => item % 2 === 0)

        console.log(result)

```

### 函数参数的默认值设置

ES6允许给函数参数赋初始值

```js
        function add(a, b, c=10){ // 具有默认值的参数，一般位置要靠后
            return a + b + c
        }
        console.log(add(1,2,))

```

可以与解构赋值一起使用

```js
        function connect({host='127.0.0.1', port, username, password}){
            console.log(host, port)
            console.log(username, password)
        }
        
        connect({
            port: 3306,
            username: 'root',
            password: 'root',
        })

```

### rest参数

ES6引入rest参数，用于获取函数的实参，用来代替arguments

```js
        // ES5获取实参的方式
        function printStudent(){
            console.log(arguments) // arguments为一个对象
        }
        printStudent('LiMing','HanMeimei')

        // ES6获取实参的方式
        function printFriend(friend1, friend2, ...rest){ // rest参数必须放在形参列表最后，否则会报错
            console.log(friend1) 
            console.log(friend2) 
            console.log(rest) // 得到一个数组，可以使用数组api
        }
        printFriend('小猫','小狗','兔子','鸭子')
        // 小猫
        // 小狗
        // ['兔子','鸭子']

```

### 扩展运算符

`...`能将「数组」转为逗号分隔的「参数序列」
 注：虽然形式与rest参数类似，但是rest参数是用在函数定义时的形参位置，扩展运算符是用在函数实际调用时的实参位置

```js
const STUDENTS = ['小明','小芳','小红']
        function printStudent(){
            console.log(arguments)
        }

        printStudent(STUDENTS) // 参数为一个数组，数组内包含3个元素
        printStudent(...STUDENTS) // 参数为3个元素
```

应用场景：

1.数组的合并

```js
        const STUDENTS1 = ['小明','小芳','小红']
        const STUDENTS2 = ['小吴', '小王']

        // es5写法
        const STUDENTS_ES5 = STUDENTS1.concat(STUDENTS2)
        // es6写法
        const STUDENTS_ES6 = [...STUDENTS1, ...STUDENTS2]

        console.log('es5------',STUDENTS_ES5)
        console.log('es6------',STUDENTS_ES6)

```

2.数组的克隆



```js
 const STUDENTS1 = ['小明','小芳','小红']

        const PUPIL = [...STUDENTS1] // 注意：如果数组内元素是引用类型，拷贝的是内存地址，为浅拷贝
        console.log('PUPIL----',PUPIL)
```

3.将伪数组转为真正的数组

```js
 const divs = document.querySelectorAll('div')
        console.log(divs) // 此处得到的divs实际是一个对象

        const divsArr = [...divs] // 将其转为真正的数组，从而可以使用数组的api譬如filter、map
        console.log(divsArr)
```

### 模板字符串

特性：

1. ` `(反引号)内容中可以直接出现换行符，’ '和" "中则不可以，出现会报错
2. 可以直接进行变量拼接

```js
// 普通字符串
`In JavaScript '\n' is a line-feed.`

// 多行字符串
`In JavaScript this is
not legal.`

// 字符串中嵌入变量
var name = "Bob", time = "today";
`Hello ${name}, how are you ${time}?`   // Hello Bob, how are you today?
```

模板字符串之中还可以调用函数。

```js
function func() {
    return 'Hello';
}

`${func()} World`;
// "Hello World"
```

### Symbol

ES6引入了一种新的原始数据类型Symbol，表示独一无二的值。它是JavaScript语言的第7种数据类型，是一个类似字符串的数据类型

#### Symbol特点：

1. Symbol的值是唯一的，用来解决命名冲突的问题
2. Symbol值不能与其他数据进行运算，也不能与自己进行运算，譬如+、-、*、/、比较运算
3. Symbol定义的对象属性不能使用for…in遍历，但是可以使用Reflect.ownKeys来获取对象的所有键名

#### 创建Symbol：

通过`let s2 = Symbol('张三')` 的方式创建Symbol，'张三’作为Symbol描述，作用相当于注释，这种方式创建的Symbol，即使传入的描述一致，但实际返回的值是不同的

```js
        // 创建Symbol
        let s = Symbol()
        console.log(s,typeof s) // Symbol() "symbol"

        let s2 = Symbol('张三') // '张三'作为Symbol描述，作用相当于注释
        let s3 = Symbol('张三') // 即使传入的描述一致，但实际返回的值是不同的
        console.log(s2 === s3) // false

```

通过`Symbol.for()`创建Symbol，这种方式创建Symbol，传入的描述一致，实际返回的值也一致，可以得到唯一的Symbol值

```js
        // Symbol.for创建Symbol
        let s4 = Symbol.for('张三')
        let s5 = Symbol.for('张三')
        console.log(s4 === s5) // true
```

#### Symbol使用场景

给对象添加属性和方法。由于Symbol值具有唯一性，所以可以很安全地把属性和方法加入对象中，如下所示

```js
        let game = {
            up: 'upp',
            down: 'doown'
        }

        let methods = {
            up: Symbol(),
            down: Symbol(),
        }

        // 添加方法
        game[methods.up] = function(){
            console.log('up up up')
        }
        game[methods.down] = function(){
            console.log('down down down')
        }

        console.log('game----', game)
        // 调用
        game[methods.up]()

```

```js
        let youxi = {
            name: '狼人杀',
            [Symbol('say')]: function(){ // 此处不能直接写 Symbol('say'): function(){...},因为Symbol('say')是动态的，和上面固定的'name'不一样
                console.log('发言')
            }
        }

```

#### Symbol内置值

ES6除了定义自己使用的Symbol值以外，还提供了11个内置的Symbol值，指向语言内部使用的方法,比如

[点这里哦]: https://blog.csdn.net/qq_41694291/article/details/103322409?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522164767121116782246439204%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&amp;request_id=164767121116782246439204&amp;biz_id=0&amp;utm_medium=distribute.pc_search_result.none-task-blog-2~all~top_positive~default-1-103322409.142^v2^pc_search_result_control_group,143^v4^register&amp;utm_term=symbol&amp;spm=1018.2226.3001.4187

### 迭代器

迭代器（iterator）是一种接口，为各种不同的数据结构提供统一的访问机制。任何数据结构只要部署iterator接口，就可以完成遍历操作

ES6创造了一种新的遍历命令for...of循环，iterator接口主要供for...of消费
注：for...of遍历的是键值，for...in遍历的是键名
for...of不能对属性值进行修改，forEach()可以

原生具备iterator接口的数据（可用for...of遍历）

```#
Array
Arguments
Set
Map
String
TypedArray
NodeList
```
#### 工作原理：

1. 创建一个指针对象，指向当前数据结构的起始位置
2. 第一次调用对象的next方法，指针自动指向数据结构的第一个成员
3. 接下来不断调用next方法，指针一直往后移动，直到指向最后一个成员
4. 每调用next方法返回一个包含value和done属性的对象，done属性表示遍历是否结束

```js
    const food = ['鱼香肉丝','糖醋里脊','酸菜鱼']
    for(let item of food){
        console.log(item)
    }

    let iterator = food[Symbol.iterator]()

    console.log(iterator.next()) // {value: "鱼香肉丝", done: false}
    console.log(iterator.next()) // {value: "糖醋里脊", done: false}
    console.log(iterator.next()) // {value: "酸菜鱼", done: false}
    console.log(iterator.next()) // {value: undefined, done: true} true 表示遍历已经结束
```

*注：需要自定义遍历数据的时候，要想到迭代器*

#### 迭代器应用-自定义遍历数据(即自己手动实现一个迭代器)

```js
        // 声明一个对象
        const school = {
            name: '三中',
            students: [
                'LiMing',
                'HanMeimei',
                'WangFang',
            ],
            [Symbol.iterator](){
                // 声明一个索引变量
                let index = 0
                return {
                    next: ()=>{
                        if(index < this.students.length){
                        // if(index < 3){
                            const result = {value: this.students[index], done: false}
                            // 下标自增
                            index++
                            // 返回结果
                            return result
                        }else{
                            return {value: undefined, done: true}
                        }
                    }
                }
            }
        }

        // 遍历这个对象
        for(let item of school){
            console.log(item)
        }

```

### 生成器

生成器本身是一个特殊的函数，生成器函数是ES6提供的一种异步编程解决方案，语法行为与传统函数不同

执行生成器函数，返回的是一个迭代器对象，通过`iterator.next()`调用执行函数内语句

```js
        function * gen(){
            console.log('hello generator')
        }
        let iterator = gen() // 返回的是一个迭代器对象
        // console.log(iterator)
        // 通过.next()调用执行函数内语句
        iterator.next() // hello generator

```

`yield`是函数代码的分隔符，结合调用`iterator.next()`方法，实现函数gen1的语句的分段执行

```js
        function * gen1(){
            console.log('--- 1 ---')
            yield '耳朵' // 函数代码的分隔符
            console.log('--- 2 ---')
            yield '尾巴'
            console.log('--- 3 ---')
        }

        let iterator1 = gen1()
        iterator1.next() // --- 1 ---
        iterator1.next() // --- 2 ---
        iterator1.next() // --- 3 ---
        // 通过调用.next()方法，实现函数gen1的语句的分段执行

```

使用`for...of`遍历函数执行后返回的迭代器对象，每一次遍历的item为yield后的表达式或者自变量的值

```js
        function * gen1(){
            yield '耳朵' // 函数代码的分隔符
            yield '尾巴'
        }

        // 遍历，每一次遍历的item为yield后的表达式或者自变量的值
        for(let item of gen1()){
            console.log(item)
        }
        // 执行结果：
        // 耳朵
        // 尾巴

        // 注：next调用和for...of调用同时存在，只会支持最先的一个

```

生成器函数的参数传递

```js
        function * gen(args){
            console.log(args) // 'aaa'
            let one = yield 111
            console.log(one) // 'bbb'

            let two = yield 222
            console.log(two) // 'ccc'
            
            let three = yield 333
            console.log(three)
        }

        // 执行生成器函数获取迭代器对象
        let iterator = gen('aaa')

        console.log(iterator.next()) // {value: 111, done: false}
        // next方法可以传入实参，传入的实参会作为上一个yield后返回的结果
        console.log(iterator.next('bbb')) // {value: 222, done: false}
        console.log(iterator.next('ccc')) // {value: 333, done: false}
        console.log(iterator.next('ddd')) // {value: undefined, done: true}

```

### 模块化

模块化是指将一个大的程序文件，拆分成许多小的文件，然后将小文件组合起来；

### 模块化的好处

模块化的优势有以下几点：

1. 防止命名冲突；
2. 代码复用；
3. 高维护性；

#### 模块化规范产品

ES6 之前的模块化规范有：

1. CommonJS => NodeJS、Browserify；
2. AMD => requireJS；
3. CMD => seaJS；

### ES6 模块化语法

模块功能主要由两个命令构成：export 和 import；

1. export 命令用于规定模块的对外接口（导出模块）；
2. import 命令用于输入其他模块提供的功能（导入模块）；

```JS
m1.js

// 分别暴露
export let school = 'atguigu'
export function teach(){
    console.log('我可以改变世界')
}


m2.js

let school = '尚硅谷'
function findJob(){
    console.log('findjob')
}
//统一暴露
export {school, findJob}


m3.js

//默认暴露
export default{
    school: 'ATGUIGU',
    change:function(){
        console.log('2333')
    }
}

```

```html
<script type="module">
    //1. 通用导入方式
    // import * as m1 from './js/m1.js'
    // import * as m2 from './js/m2.js'
    // import * as m3 from './js/m3.js'
    // m3.default.change()

    //2. 解构赋值形式
    import {school, teach} from './js/m1.js'
    // console.log(school)
    // console.log(teach)
    // 可以设置别名来区分变量
    import {school as guigu, findJob} from './js/m2.js'
    // console.log(guigu,findJob)
    // 导入默认暴露的模块：必须起一个别名
    // import {default as m3} from './js/m3.js'

    //3. 简便形式 只能导入默认暴露
    import m3 from './js/m3.js'
    console.log(m3)
</script>

```

### ES7新特性
#### Array的includes

用来判断元素在不在数组

```js
const s = ["AA","BB","CC","DD"]
console.log(s.includes("BB"))   // true
console.log(s.includes("EE"))   // false
```

#### **运算符

与python的**一样，用来算指数，Math.pow()功能一样

```js
console.log(Math.pow(5,3))    // 125
console.log(5**3)             // 125
```

### ES8新特性
#### async & await

async/await是一种新的异步函数同步解决方案

##### async

- async可以放在函数前，定义async函数，这种函数的返回值是会被转化为Promise
- async函数的返回值如果是是非Promise对象，那么会将return val的结果转化为Promise.resolve(val), 即使val- undefined
- async函数中如果抛出异常，那么会返回Promise.reject
- async函数如果返回Promise对象，那么会直接返回
- 不能在全局直接声明async函数，实在不行可以写成
- (async()=>{})()
- 的立即执行函数

##### await

- await必须写在async函数中
- await右侧的表达式一般是Promise对象，也可以是正常值
- await的结果是Promise成功的值，如果Promise的结果是reject,那么会抛出异常

详见Promise内容

#### 对象方法的扩展

```js
Object.keys()获取对象所有的键名，返回值是数组

let lower = {
  "A":"a",
  "B":"b",
  "C":"c",
  "D":"d",
}

Object.keys(lower).forEach(d=>console.log(d))  // A B C D

Object.values()获取对象所有的值，返回值是数组

let lower = {
  "A":"a",
  "B":"b",
  "C":"c",
  "D":"d",
}

console.log(Object.values(lower))
// [ 'a', 'b', 'c', 'd' ]


Object.entries()获取对象所有的键值对，返回值是数组，元素是一个数组，包含键和值, 可以用来构造Map

let lower = {
  "A":"a",
  "B":"b",
  "C":"c",
  "D":"d",
}
console.log(Object.entries(lower))
// [ [ 'A', 'a' ], [ 'B', 'b' ], [ 'C', 'c' ], [ 'D', 'd' ] ]
let m = new Map(Object.entries(lower))
console.log(m)
// Map(4) { 'A' => 'a', 'B' => 'b', 'C' => 'c', 'D' => 'd' }
```
#### Object.getOwnPropertyDescriptors()

获取对象属性的描述对象，这个对象的每一个属性都对应描述中的一个对象，包括值，可写，可删除，可枚举，方便我们进行深层次的对象克隆

```js
let lower = {
    "name": "a",
    "age": 12,
    "sex": "F",
    "note": "good",
}

console.log(Object.getOwnPropertyDescriptors(lower))
/**
{
    name: { value: 'a', writable: true, enumerable: true, configurable: true },
    age: { value: 12, writable: true, enumerable: true, configurable: true },
    sex: { value: 'F', writable: true, enumerable: true, configurable: true },
    note: {
        value: 'good',
        writable: true,
        enumerable: true,
        configurable: true
    }
}
*/
```

### ES9新特性

#### REST参数与Spread扩展

在ES6中只有对数组的REST/Spread, 在ES9中支持对对象进行REST/Spread

**REST**

```js
function cnnt({host,port,...args}){
    console.log(host);
    console.log(port);
    console.log(args);          // 对象的rest就是一个对象
}

cnnt({
    host: "127.0.0.1",
    port: 80,
    pwd: 123,
    type: "A"
})
// 127.0.0.1
// 80
// { pwd: 123, type: 'A' }

```

```js
let Obj1={
    "name":"Liu"
}

let Obj2={
    "Sex":"M"
}

let Obj3={
    "Age":20
}

let res = {...Obj1,...Obj2,...Obj3}
console.log(res)
// { name: 'Liu', Sex: 'M', Age: 20 }

```

### 正则扩展

#### **命名捕获分组**

我们可以对政策匹配到的分组`$1,$2...`赋名，方面我们的使用

在之前

```js
let str = '<iframe class="notranslate">Inner</iframe>';
// 想要获取class和标签内容要写两个()用来分组
let reg = /class="(.*)\".*>(.*)<\/iframe/;
let res = reg.exec(str);
console.log(res);
```

结果是

```js
[
  'class="notranslate">Inner</iframe',
  'notranslate',
  'Inner',
  index: 8,
  input: '<iframe class="notranslate">Inner</iframe>',
  groups: undefined       // 这里是undefined
]

```

也就是res[0]是匹配结构,res[1]是第一个分组,res[2]是第二个分组

将需要赋值的分组括号由`(条件)`改为`(?<变量名>条件)`,使用捕获分组会存储着groups中

```js
let str = '<iframe class="notranslate">Inner</iframe>';
// 想要获取class和标签内容要写两个()用来分组
let reg = /class="(?<cls>.*)\".*>(?<Inn>.*)<\/iframe/;
let res = reg.exec(str);
console.log(res);
console.log(res.groups.cls);
console.log(res.groups.Inn);
```

结果是

```js
[
  'class="notranslate">Inner</iframe',      // [0-2]都没有变
  'notranslate',
  'Inner',
  index: 8,
  input: '<iframe class="notranslate">Inner</iframe>',
  groups: [Object: null prototype] { cls: 'notranslate', Inn: 'Inner' }
  // groups变了
]
notranslate       // 可以直接输出了
Inner

```

就可以直接使用对应变量了,在修改正则的时候也不用修改下标了

#### 反向断言

正向断言是匹配某个串要求不仅要满足串的条件,原串后面的内容也要满足指定条件,例如: 对于子复查u年’aaa111bbb222’我想要最后一个连续的字母,那么应该匹配的是[a-zA-Z]+并且后面是2实现方法是在正则条件后加上(?=后面的内容),这里要匹配的内容不用分组,因为我们这个方法就是要一次性匹配到结果

```js
let str = 'aaa111bbb222';
let reg = /[a-zA-Z]+(?=2)/
let res = reg.exec(str);
console.log(res)
// [ 'bbb', index: 6, input: 'aaa111bbb222', groups: undefined ]
```

反向断言是要匹配一个串,满足串前面的内容是指定条件.实现方法是**(?<=前面的内容)条件**,例如我想匹配第一个出现的数字串

```js
let str = 'aaa111bbb222';
let reg = /(?<=a)[0-9]+/
let res = reg.exec(str);
console.log(res)
// [ '111', index: 3, input: 'aaa111bbb222', groups: undefined ]
```

dotAll模式

在正则中.代表任意除\n外的任意内容,在提取有\n的内容的时候就显得不方便,只需要设置/条件/s即可,就是在最后加入s属性

.*用来匹配任意字符串的时候经常出现贪婪匹配,可以设置.*?禁止贪婪

### ES10新特性

- `Object.entries()`可以获取对象所有的**键值对**，返回值是数组，元素是一个数组，包含键和值, 可以用来构造Map
- `Object.fromEntries()`可以将一个Map/二维数组转化为对象的形式

```js
let ary = [
    ['A','a'],
    ['B','b'],
    ['C','c'],
    ['D','d'],
];

let res = Object.fromEntries(ary);
console.log(res)
// { A: 'a', B: 'b', C: 'c', D: 'd' }
```

#### trimStart/trimEnd方法

在ES5中字符串有trim方法用来清除字符串两边的空白, 现在有start/end指定清除哪一边了空白

```js
let s = '   abc     ';
console.log(s.trim(),s.trim().length)   //abc 3
console.log(s.trimStart(),s.trimStart().length)   //abc      8
console.log(s.trimEnd(),s.trimEnd().length)   //   abc 6
```

#### Array.flat/flatMap方法

lat译为平面,也就是可以将数组内部数组的元素维度降低,例如

```js
let arr1 = [1,2,[3,4]];
let arr2 = [1,2,[3,4,[5,6]]];

console.log(arr1.flat());         // [ 1, 2, 3, 4 ]
console.log(arr2.flat());         // [ 1, 2, 3, 4, [ 5, 6 ] ]
console.log(arr2.flat().flat());  // [ 1, 2, 3, 4, 5, 6 ]
console.log(arr2.flat(2));        // [ 1, 2, 3, 4, 5, 6 ] 可以在括号中指定深度,默认1
```

flatMap可以将map的结果进行降维,这里的map和Map不同,类似于python的map做批量操作

```js
let arr = [1,2,3,4];

let res1 = arr.map(item => item*10)
console.log(res1)
// [ 10, 20, 30, 40 ]
let res2 = arr.map(item => [item*10,item*10+1])
console.log(res2)
// [ [ 10, 11 ], [ 20, 21 ], [ 30, 31 ], [ 40, 41 ] ]
let res3 = arr.flatMap(item => [item*10,item*10+1])
console.log(res3)
// [ 10, 11, 20, 21, 30, 31, 40, 41 ]
```

#### Symbol.description方法

可以用`Symbol.description`方法获取Symbol的注释

```js
let s = Symbol("我是一个注释")
console.log(s.description)  // 我是一个注释
```

### ES11新特性

#### 私有属性

在传统OOP语言中的对象可以是私有的,ES11引入了这个特性, 定义私有属性只要在前面加入`#`就可以了

```js
class Psn{
    name;       // 公有的
    #age;       // 私有的
    constructor(name,age){
        this.name = name;
        this.#age = age;
    }
    getIt(){
        return {"N":this.name,"A":this.#age};
    }
}

let psn = new Psn("Liu",12);
console.log(psn.getIt());  // { N: 'Liu', A: 12 }
console.log(psn.name)      // Liu
console.log(psn.#age)      // Error
```

#### Promise.allSettled方法

可以指定一个变量为`Promise.allSettled()`, 他会运行一系列Promise,当全部运行结束后,不论他包含的Promise的结果是什么,状态都变为resolved,并保存每个Promise的结果

```js
let p1 = new Promise((res,rej)=>{
    setTimeout(()=>{
        console.log("OK");
        res("Im P1");
    },1000);
})

let p2 = new Promise((res,rej)=>{
    setTimeout(()=>{
        console.log("NK");
        rej("Im P2");
    },1000);
})

let p3 = new Promise((res,rej)=>{
    setTimeout(()=>{
        console.log("OK");
        res("Im P3");
    },1000);
})

let result = Promise.allSettled([p1,p2,p3]);
console.log(result)
setTimeout(()=>console.log(result),5000)            // 延时显示等待Promise结束
```

结果是

```js
Promise { <pending> }
OK
NK
OK
Promise {
  [
    { status: 'fulfilled', value: 'Im P1' },
    { status: 'rejected', reason: 'Im P2' },
    { status: 'fulfilled', value: 'Im P3' }
  ]
}
```

与他很像的是`Promise.all()`方法,他的结果是所有结果取`AND`,他们都用来做批量异步任务, all一般是用来做前一个成功后一个运行,allSettled一般是要全部运行, 之间没有关联, 要求保存结果

#### String.matchAll方法

如果正则表达式有/g标志，那么多次调用.exec()就会得到所有匹配的结果。如果没有匹配的结果，.exec()就会返回null。在这之前会返回每个匹配的匹配对象。这个对象包含捕获的子字符串和更多信息.如果正则表达式没有/g标志，.exec()总是返回第一次匹配的结果。

```js
const matchIterator = str.matchAll(regExp);
```

给定一个字符串和一个正则表达式，.matchAll（）为所有匹配的匹配对象返回一个迭代器。也可以使用一个扩展运算符…把迭代器转换为数组。

```js
[...'-a-a-a'.matchAll(/-(a)/ug)]
//[ [ '-a', 'a' ], [ '-a', 'a' ], [ '-a', 'a' ] ]
```

现在是否设置/g，都不会有问题了。

```js
[...'-a-a-a'.matchAll(/-(a)/u)]
// [ [ '-a', 'a' ], [ '-a', 'a' ], [ '-a', 'a' ] ]
```

### 可选链操作符号

在以前我们想访问一个对象很深的属性要进行多次尝试防止出现访问`undefined.XXX`,例如

```js
let d = {
  name:{
    fname:{
      pub: true,
      value: "Liu"
    },
    lname:{
      pub : false,
    }
  }
}

let fnm = d.name&&d.name.fname&&d.name.fname.value    // 要一直尝试
let lnm = d.name&&d.name.lname&&d.name.lname.value    // 要一直尝试
console.log(fnm,lnm)    // Liu undefined

```

可选链的操作符是`?.`,例如`A?.B`就是A存在才去读取B,例如

```js
let d = {
  name:{
    fname:{
      pub: true,
      value: "Liu"
    },
    lname:{
      pub : false,
    }
  }
}

let fnm = d?.name?.fname?.value
let lnm = d?.name?.lname?.value
console.log(fnm,lnm)    // Liu undefined
```

#### 动态Import

动态导入支持按需加载模块/懒加载,而不是一股脑的在开头加载,语法是`import("path")`,返回的是一个Promise对象,当正确加载就resolve, resolve的值是模块暴露的对象

静态导入

```js
// 文件头
import * as md1 from "./demo.js"
12
```

动态导入

```js
if(something){
  import("./demo.js").then((d)=>{
    d.xx();     // d就是暴露的对象
  })
}
```

### BigInt类型

比int类范围大,用于大数运算

- 字面值写法: `123n`
- Int转BigInt:`BigInt(123)`
- BigInt不能和int进行运算,必须把int转为BigInt,例如

```js
let i = 123n
console.log(i)              // 123n
console.log(i+10)           // Error
console.log(i+BigInt(10))   // 133n
```

#### 绝对全局对象

浏览器的全局对象是window, 但是NodeJS等没有window, 在新的NodeJS/浏览器中都可以使用`golbalThis`指向全局对象, 使得在浏览器/NodeJS中编程得到了一个统一

```
// @Node
console.log(globalThis)
// <ref *1> Object [global] {
//   global: [Circular *1],
//   clearInterval: [Function: clearInterval],
//   clearTimeout: [Function: clearTimeout],
//   setInterval: [Function: setInterval],
//   setTimeout: [Function: setTimeout] {
//     [Symbol(nodejs.util.promisify.custom)]: [Getter]
//   },
//   queueMicrotask: [Function: queueMicrotask],
//   performance: [Getter/Setter],
//   clearImmediate: [Function: clearImmediate],
//   setImmediate: [Function: setImmediate] {
//     [Symbol(nodejs.util.promisify.custom)]: [Getter]
//   }
// }

// @Chrome
console.log(globalThis)
// Window {0: Window, 1: Window, window: Window, self: Window, document: document, name: "", location: Location, …}

```

### ES12新特性

#### replaceAll

看到replaceAll这个词，相比很容易联想到replace。在JavaScript中，replace方法只能是替换字符串中匹配到的第一个实例字符，而不能进行全局多项匹配替换，唯一的办法是通过正则表达式进行相关规则匹配替换

而replaceAll则是返回一个全新的字符串，所有符合匹配规则的字符都将被替换掉，替换规则可以是字符串或者正则表达式。

```js
let string = 'I like 前端,I like 前端公虾米'
//使用replace
let replaceStr = string.replace('like','love')
console.log(replaceStr)  // 'I love 前端,I like前端公虾米'
//replace使用正则匹配所有
console.log(string.replace(/like/g,'love')) // 'I love 前端,I love 前端公虾米'
//使用replaceAll
let replaceAllStr = string.replaceAll('like','love')
console.log(replaceAllStr) // 'I love 前端,I love 前端公虾米'
```

需要注意的是，replaceAll在使用正则表达式的时候，如果非全局匹配（/g），则replaceAll()会抛出一个异常

#### Promise.any

当Promise列表中的任意一个promise成功resolve则返回第一个resolve的结果状态

如果所有的promise均reject，则抛出异常表示所有请求失败

```js
Promise.any([
  new Promise((resolve, reject) => setTimeout(reject, 500, '哎呀，我被拒绝了')),
  new Promise((resolve, reject) => setTimeout(resolve, 1000, '哎呀，她接受我了')),
  new Promise((resolve, reject) => setTimeout(resolve, 2000, '哎呀，她也接受我了')),
])
.then(value => console.log(`输出结果: ${value}`))
.catch (err => console.log(err))

//输出
//输出结果:哎呀，她接受我了
```

再来看下另一种情况

```js
Promise.any([
  Promise.reject('Error 1'),
  Promise.reject('Error 2'),
  Promise.reject('Error 3')
])
.then(value => console.log(`请求结果: ${value}`))
.catch (err => console.log(err))

//输出
AggregateError: All promises were rejected
```

Promise.any与Promise.race十分容易混淆，务必注意区分，Promise.race 一旦某个promise触发了resolve或者reject，就直接返回了该状态结果，并不在乎其成功或者失败
