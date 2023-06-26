---
title: HTML5笔记
tags:
  - HTML5

---

**本文作者**[秋一](https://godv.cc/readme/)

### <!DOCTYPE>

- `<!DOCTYPE>` 声明位于文档中的最前面的位置，处于 `<html>` 标签之前。
- `<!DOCTYPE>` 不是一个 HTML 标签，它就是文档类型声明标签。

### lang 语言种类

- en 定义语言为英语

- zh-CN 定义语言为中文

  `<html lang=en>`

### 文本格式化标签

| 语义   | 标签                     |
| ------ | ------------------------ |
| 加粗   | `<strong></strong>`      |
| 倾斜   | ` <em><em> ``<i></i> `   |
| 删除线 | ` <del></del>``<i></i> ` |
| 下划线 | `<ins></ins> <u>`        |
| 水平线 | `<hr>`(屏幕中一道大横线) |

### img

| 属性  | 属性值   | 说明                                     |
| ----- | -------- | ---------------------------------------- |
| src   | 图片路径 | 必须属性                                 |
| alt   | 文本     | 替换文本（当图片不能显示时候显示的文字） |
| title | 文本     | 提示文本（鼠标放到图像上，显示的文字）   |

### a

| 属性   | 作用                                                                  |
| ------ | --------------------------------------------------------------------- |
| href   | 用于指定链接目标的 url 地址。必须属性                                 |
| target | 用于指定连接页面的打开方式。`_self`为默认值，`_blank`为在新窗口中打开 |

### 锚点链接

```html
<a href="#two">第二季</a>
<h3 id="two">第二季介绍</h3>
```

### 表格标签

- table 用来定义表格的标签
- tr 用来定义表格中的行，必须嵌套在`<table></table>` 标签中
- td 用来定义表格中的单元格，必须嵌套在`<tr></tr>` 标签中
- th 用来定义表格中的表头，表头单元格里面的内容加粗居中显示

```html
<table>
  <thead>
    <tr>
      <th>姓名</th>
      <th>性别</th>
      <th>年龄</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>林晓</td>
      <td>男</td>
      <td>18</td>
    </tr>
    <tr>
      <td>林晓</td>
      <td>男</td>
      <td>18</td>
    </tr>
    <tr>
      <td>林晓</td>
      <td>男</td>
      <td>18</td>
    </tr>
  </tbody>
  <tfooter></tfooter>
</table>
```

### 自定义列表 dl

里面只能包含 dt 和 dd，dt 和 dd 里面可以放任何标签

```html
<dl>
  <dt>关注我们</dt>
  <dd>新浪微博</dd>
  <dd>联系我们</dd>
</dl>
```

### 表单标签

一个完整的表单通常由**表单域，表单控件（表单元素）和提示信息**3 部分组成

#### 表单域

- 表单域是一个包含表单元素的区域
- `<form></from>`标签用于定义表单域，会把它范围内的表单元素信息提交给服务器

| 属性   | 属性值   | 作用                                               |
| ------ | -------- | -------------------------------------------------- |
| action | url 地址 | 用于指定接收并处理表单数据的服务器程序的 url 地址  |
| method | get/post | 用于设置表单数据的提交方式，其取值为 get 或 post   |
| name   | 名称     | 用于指定表单的名称，以区分同一个页面中的多个表单域 |

#### input 输入表单元素

| 属性值   | 描述                                                             |
| -------- | ---------------------------------------------------------------- |
| button   | 定义可点击按钮(多数情况下，用于通过 JavaScript 启动脚本)         |
| checkbox | 定义复选框                                                       |
| file     | 定义输入字段和"浏览"按钮，供文件上传。                           |
| hidden   | 定义隐藏的输入字段                                               |
| image    | 定义图像形式的提交按钮                                           |
| password | 定义密码字段。该字段中的字符被掩码                               |
| radio    | 定义单选按钮                                                     |
| reset    | 定义重置按钮。重置按钮会清楚表单中的所有数据。                   |
| submit   | 定义提交按钮。提交按钮会把表单数据发送到服务器。                 |
| text     | 定义单行的输入字段，用户可在其中输入文本。默认宽度为 20 个字符。 |

- name 和 value 是每个表单元素都有的属性值，主要给后端人员使用。
- name 是表单元素的名字，要求 单选框和复选框要有相同的 name 值
- checked 属性主要针对于单选框和复选框，主要作用是一打开页面，就可以默认选中某个表单元素
- `maxlength`:规定最多输入多少个字符

#### label

```html
<label for="sex"> 男 </lable>
<input type="radio" name="sex" id="sex" />
```

#### select 下拉表单元素

下拉表单元素
`<select>`中至少包含一对`<option>`
在`<option>`中定义 `selected="selected"` 时，当前项即为默认选中项。

```html
<select>
  <option selected="selected">选项1</option>
  <option>选项2</option>
  <option>选项3</option>
  ...
</select>
```

#### textarea 文本域元素

- 用于定义多行文本输入的控件

```html
<textarea>
    文本内容
</textarea>
```

### 新增语义化标签

以前布局，我们基本用 div 来做。 div 对于搜索引擎来说，是没有语义的。

新增语义化标签如下：

![](https://img-blog.csdnimg.cn/07df0702684841339d1b4884b4bdc677.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L0F1Z2Vuc3Rlcm5fUVhM,size_16,color_FFFFFF,t_70#pic_center)

- < header > :头部标签
- < nav >: 导航标签
- < article >：内容标签
- < section >:定义文档某个区域
- < aside >:侧边栏标签
- < footer >: 尾部标签

### video 视频

```html
<video src="文件地址"   controls="controls"></video>

<style>
        video {
            width: 100%;
        }
    </style>
</head>
<body>
    <video src="media/mi.mp4" autoplay="autoplay" muted="muted"  loop="loop" poster="media/mi9.jpg"></video>
</body>
```

| 属性     | 值           | 描述                                                              |
| -------- | ------------ | ----------------------------------------------------------------- |
| autoplay | autoplay     | 视频就绪自动播放(**谷歌浏览器需要添加 muted 来解决自动播放问题**) |
| controls | controls     | 向用户显示播放控件                                                |
| width    | pixels(像素) | 设置播放器宽度                                                    |

| height  | pixels(像素)                         | 设置播放器高度                                     |
| ------- | ------------------------------------ | -------------------------------------------------- |
| loop    | loop                                 | 播放完是否继续播放该视频,循环播放                  |
| preload | auto(预先加载视频)none(不应加载视频) | 规定是否预加载视频(如果有了 autoplay 就忽略该属性) |

| src    | url    | 视频 url 的地址    |
| ------ | ------ | ------------------ |
| poster | lmgurl | 加载等待的画面图片 |
| muted  | muted  | 静音播放           |

1：下面布局不对，很可能是上面浮动的问题。（例如 上面某个文字行高超出了）

2：如果是行高小于盒子高度，文字会偏上，如果行高大于盒子高度，则文字偏下

3：固定定位要有宽度，固定定位跟父级没有关系，她以屏幕为准

4：c3 盒子模型，里面的文字的行号应该小一点

5：linear-gradient 背景渐变必须添加浏览器私有前缀-webkit-

6：当我们为父盒子设为 flex 布局以后，子元素的 float、clear 和 vertical-align 属性将失效。

### audio 音频

```html
audio src="文件地址" controls="controls"></audio>

<audio src="media/music.mp3" autoplay="autoplay" controls="controls"></audio>
------------------------------------------------------------------------------------------------
<audio id="meowClip" controls>
  <source src="audio/meow.mp3" type="audio/mpeg">
  <source src="audio/meow.ogg" type="audio/ogg">
</audio>
```

| 属性     | 值       | 描述                                           |
| -------- | -------- | ---------------------------------------------- |
| autoplay | autoplay | 如果出现该属性，则音频在就绪后马上播放         |
| controls | controls | 如果出现该属性，则向用户显示控件，比如播放按钮 |
| loop     | loop     | 如果出现该属性，则每当音频结束时重新开始播放   |
| src      | url      | 要播放的音频的 url                             |

1. 音频标签和视频标签使用方式基本一致
2. 浏览器支持情况不同
3. **谷歌浏览器把音频和视频自动播放禁止了**
4. 我们可以给视频标签添加 muted 属性来静音播放视频，音频不可以(可以通过 JavaScript 解决)
5. 视频标签是重点，我们经常设置自动播放，不适用 controls 控件，循环和设置大小属性

### 新增 input 类型

| 属性值       | 说明                          |
| ------------ | ----------------------------- |
| type=“email” | 限制用户输入必须为 Email 类型 |
| type=“url”   | 限制用户输入必须为 URL 类型   |
| type=“data”  | 限制用户输入必须为日期类型    |
| type=“time”  | 限制用户输入必须为时间类型    |
| type=“month” | 限制用户输入必须为月类型      |

| type=“week”       | 限制用户输入必须为周类型       |
| ----------------- | ------------------------------ |
| **type="number"** | **限制用户输入必须为数字类型** |
| **type="tel"**    | **手机号码**                   |
| **type="search"** | **搜索框**                     |
| type=“color”      | 生成一个颜色选择表单           |

### 新增表单属性

|      属性       |      值      |                                                                                             说明                                                                                              |
| :-------------: | :----------: | :-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------: |
|    required     |   required   |                                                                            表单拥有该属性表示其内容不能为空，必填                                                                             |
| **placeholder** | **提示文本** |                                                                            **表单的提示信息，存在默认值将不显示**                                                                             |
|    autofocus    |  autofocus   |                                                                         自动聚焦属性，页面加载完成自动聚焦到指定表单                                                                          |
|  autocomplete   |    off/on    | 当用户在字段开始键入时，浏览器基于之前键入过的值，应该显示出在字段中填写的选项，默认已经打开。如 autocomplete=“on” ,关闭 autocomplete=“off”，需要放在表单内，同时加上 name 属性，同时成功提交 |
|  **multiple**   | **multiple** |                                                                                     **可以多选文件提示**                                                                                      |

- 可以通过以下设置方式修改 placeholder 里面的字体颜色

```css
input::placeholder {
  color: pink;
}
```

### figure

**使用 figure 元素提高图表的可访问性**

HTML5 引入了 `figure` 标签以及与之相关的 `figcaption` 标签。 它们一起用于展示可视化信息（如：图片、图表）及其标题。 这样通过语义化对内容进行分组并配以用于解释 `figure` 的文字，可以极大地提升内容的可访问性

```html
<figure>
  <img
    src="roundhouseDestruction.jpeg"
    alt="Photo of Camper Cat executing a roundhouse kick"
  />
  <br />
  <figcaption>
    Master Camper Cat demonstrates proper form of a roundhouse kick.
  </figcaption>
</figure>
```

### fieldset

**将单选按钮包裹在 fieldset 元素中以获得更好的可访问性**

`fieldset` 标签包裹整组单选按钮，实现这个功能。 它经常使用 `legend` 标签来提供分组的描述，以便屏幕阅读器用户会阅读 `fieldset` 元素中的每个选项。

当选项的含义很明确时，如“性别选择”，`fieldset` 与 `legend` 标签可以省略。 这时，使用包含 `for` 属性的 `label` 标签就足够了

```html
<form>
  <fieldset>
    <legend>Choose one of these three items:</legend>
    <input id="one" type="radio" name="items" value="one" />
    <label for="one">Choice One</label><br />
    <input id="two" type="radio" name="items" value="two" />
    <label for="two">Choice Two</label><br />
    <input id="three" type="radio" name="items" value="three" />
    <label for="three">Choice Three</label>
  </fieldset>
</form>
```

### accesskey

27：**通过给元素添加 accesskey 属性来让用户可以在链接之间快速导航**

HTML 提供 `accesskey` 属性，用于指定激活元素或者使元素获得焦点的快捷键。 添加 `accesskey` 属性可以让使用键盘的用户更高效率地导航。

HTML5 允许在任何标签上使用这个属性。 该属性尤其适用于链接、按钮、表单组件等元素。

```html
<button accesskey="b">Important Button</button>
```

### tabindex

28：**使用 tabindex 将键盘焦点添加到元素中**

HTML 的 `tabindex` 属性有三种与标签焦点相关的功能。 当它在一个元素上时，表示该元素可以获得焦点。 tabindex 的值（可以是零、负整数或正整数）定义了行为。

当用户使用键盘浏览页面时，诸如链接、表单控件等元素可以自动获得焦点。 它们获得焦点的顺序与它们出现在 HTML 文档流中的顺序一致。 我们可以通过将其他标签（如 `div`、`span`、`p` 等）的 `tabindex` 属性值设为 0 来让它们实现类似的效果。 比如：

```html
<div tabindex="0">I need keyboard focus!</div>
```

`tabindex` 属性还可以指定元素的 tab 键焦点顺序， 将它的值设置为大于等于 1 的整数，就可以实现这个功能。

给元素设置 `tabindex="1"`，键盘将首先把焦点放在这个元素上。 然后它按照指定的 `tabindex` 值（2、3 等等）顺序循环，再移动到默认值和 `tabindex="0"` 项目
