---
title: 使用css做按钮节流
tags:
  - CSS
# categories:
#   - 前端
---

还在用 JS 做节流吗？CSS 也可以防止按钮重复点击


众所周知，函数节流（throttle）是 JS 中一个非常常见的优化手段，可以有效的避免函数过于频繁的执行。

举个例子：一个保存按钮，为了避免重复提交或者服务器考虑，往往需要对点击行为做一定的限制，比如只允许每`300ms`提交一次，这时候我想大部分同学都会到网上直接拷贝一段`throttle`函数，或者直接引用`lodash`工具库

<table><tbody><tr><td class="gutter"><pre><span class="line">1</span><br></pre></td><td class="code"><pre><span class="line">btn.<span class="title function_">addEventListener</span>(<span class="string">"click"</span>, _.<span class="title function_">throttle</span>(save, <span class="number">300</span>));</span><br></pre></td></tr></tbody></table>

其实除了 JS 方式， CSS 也可以非常轻易的实现这样一个功能，无需任何框架库，一起看看吧

[](about:blank#%E4%B8%80%E3%80%81CSS-%E5%AE%9E%E7%8E%B0%E6%80%9D%E8%B7%AF%E5%88%86%E6%9E%90 "一、CSS 实现思路分析")一、CSS 实现思路分析
-----------------------------------------------------------------------------------------------------------------------

CSS 实现和 JS 的思维不同，需要从另一个角度去看待这个问题。

比如这里的需要对点击事件进行限制，也就是禁用点击事件，想想有什么方式可以禁用事件，没错，就是`pointer-events`;

然后是时间的限制，每次点击后需要自动禁用`300ms`，时间过后重新恢复，那么，有什么特性和时间以及状态恢复有关呢？没错，就是`animation`;

除此之外，还需要有触发时机，这里是点击行为，所以必然和伪类`:active`有关联。

因此，综合分析，实现这样一个功能需要用到`pointer-events`、`animation`以及`:active`，那么如何将这些思路串联起来呢？

![image-20221112001600031](data:image/gif;base64,R0lGODlhAQABAIAAAAAAAP///yH5BAEAAAAALAAAAAABAAEAAAIBRAA7)

思考 3 秒…

🤔

🤔

🤔

你想到了吗？💡💡💡

其实这种场景可以理解成是**对 CSS 动画的控制**，比如有一个动画控制按钮从**禁用**\->**可点击**的变化，每次点击时让这个动画重新执行一遍，在执行的过程中，一直处于**禁用**状态，是不是就达到了“节流”的效果了？

接下来看看具体实现

[](about:blank#%E4%BA%8C%E3%80%81CSS-%E5%8A%A8%E7%94%BB%E7%9A%84%E7%B2%BE%E5%87%86%E6%8E%A7%E5%88%B6 "二、CSS 动画的精准控制")二、CSS 动画的精准控制
----------------------------------------------------------------------------------------------------------------------------------

假设有一个按钮，绑定了一个点击事件

<table><tbody><tr><td class="gutter"><pre><span class="line">1</span><br></pre></td><td class="code"><pre><span class="line"><span class="tag">&lt;<span class="name">button</span> <span class="attr">onclick</span>=<span class="string">"console.log('保存')"</span>&gt;</span>保存<span class="tag">&lt;/<span class="name">button</span>&gt;</span></span><br></pre></td></tr></tbody></table>

这时的按钮连续点击就会不断地触发，效果如下

![Kapture 2022-11-12 at 00.17.44](data:image/gif;base64,R0lGODlhAQABAIAAAAAAAP///yH5BAEAAAAALAAAAAABAAEAAAIBRAA7)

下面定义一个关于`pointer-events`的动画，就叫做 `throttle` 吧

<table><tbody><tr><td class="gutter"><pre><span class="line">1</span><br><span class="line">2</span><br><span class="line">3</span><br><span class="line">4</span><br><span class="line">5</span><br><span class="line">6</span><br><span class="line">7</span><br><span class="line">8</span><br></pre></td><td class="code"><pre><span class="line"><span class="keyword">@keyframes</span> throttle {</span><br><span class="line">  <span class="selector-tag">from</span> {</span><br><span class="line">    <span class="attribute">pointer-events</span>: none;</span><br><span class="line">  }</span><br><span class="line">  <span class="selector-tag">to</span> {</span><br><span class="line">    <span class="attribute">pointer-events</span>: all;</span><br><span class="line">  }</span><br><span class="line">}</span><br></pre></td></tr></tbody></table>

很简单吧，就是从**禁用**到**可点击**的变化。

接下来，将这个动画绑定在按钮上，这里为了方便测试，将动画设置成了`2s`

<table><tbody><tr><td class="gutter"><pre><span class="line">1</span><br><span class="line">2</span><br><span class="line">3</span><br></pre></td><td class="code"><pre><span class="line"><span class="selector-tag">button</span> {</span><br><span class="line">  <span class="attribute">animation</span>: throttle <span class="number">2s</span> step-end forwards;</span><br><span class="line">}</span><br></pre></td></tr></tbody></table>

注意，这里动画的缓动函数设置成了阶梯曲线，`step-end`，它可以很方便的控制`pointer-events`的变化时间点。

> 有兴趣的可以参考这篇文章：[CSS3 animation 属性中的 steps 功能符深入介绍 « 张鑫旭-鑫空间-鑫生活 (zhangxinxu.com)](https://link.juejin.cn/?target=https://www.zhangxinxu.com/wordpress/2018/06/css3-animation-steps-step-start-end/ "https://www.zhangxinxu.com/wordpress/2018/06/css3-animation-steps-step-start-end/")

如下示意，`pointer-events`在 0~2 秒内的值都是`none`，一旦到达 2 秒，就立刻变成了`all`，由于是`forwards`，会一直保持`all`的状态

![image-20221112005210875](data:image/gif;base64,R0lGODlhAQABAIAAAAAAAP///yH5BAEAAAAALAAAAAABAAEAAAIBRAA7)

最后，在点击时重新执行一遍动画，只需要在按下时设置动画为`none`就行了

> 这个技巧之前在这篇文章中有更详细的介绍： [CSS 实现按钮点击动效的套路](https://juejin.cn/post/7064404257436336135 "https://juejin.cn/post/7064404257436336135")

实现如下

<table><tbody><tr><td class="gutter"><pre><span class="line">1</span><br><span class="line">2</span><br><span class="line">3</span><br></pre></td><td class="code"><pre><span class="line"><span class="selector-tag">button</span><span class="selector-pseudo">:active</span> {</span><br><span class="line">  <span class="attribute">animation</span>: none;</span><br><span class="line">}</span><br></pre></td></tr></tbody></table>

为了演示方便，我们暂时把颜色变化也加在动画里

<table><tbody><tr><td class="gutter"><pre><span class="line">1</span><br><span class="line">2</span><br><span class="line">3</span><br><span class="line">4</span><br><span class="line">5</span><br><span class="line">6</span><br><span class="line">7</span><br><span class="line">8</span><br><span class="line">9</span><br><span class="line">10</span><br></pre></td><td class="code"><pre><span class="line"><span class="keyword">@keyframes</span> throttle {</span><br><span class="line">  <span class="selector-tag">from</span> {</span><br><span class="line">    <span class="attribute">color</span>: red;</span><br><span class="line">    <span class="attribute">pointer-events</span>: none;</span><br><span class="line">  }</span><br><span class="line">  <span class="selector-tag">to</span> {</span><br><span class="line">    <span class="attribute">color</span>: green;</span><br><span class="line">    <span class="attribute">pointer-events</span>: all;</span><br><span class="line">  }</span><br><span class="line">}</span><br></pre></td></tr></tbody></table>

现在如果文字是`red`，表示是禁用态，只有是`green`，才表示可以被点击，非常清晰明了，如下

![Kapture 2022-11-12 at 10.54.43](data:image/gif;base64,R0lGODlhAQABAIAAAAAAAP///yH5BAEAAAAALAAAAAABAAEAAAIBRAA7)

下面是最终点击对比效果，很好地限制了点击频率

![Kapture 2022-11-12 at 10.48.13](data:image/gif;base64,R0lGODlhAQABAIAAAAAAAP///yH5BAEAAAAALAAAAAABAAEAAAIBRAA7)

完整代码如下，就这么几行，**如果需要改限制时间，直接改动画时间就行了**

<table><tbody><tr><td class="gutter"><pre><span class="line">1</span><br><span class="line">2</span><br><span class="line">3</span><br><span class="line">4</span><br><span class="line">5</span><br><span class="line">6</span><br><span class="line">7</span><br><span class="line">8</span><br><span class="line">9</span><br><span class="line">10</span><br><span class="line">11</span><br><span class="line">12</span><br><span class="line">13</span><br><span class="line">14</span><br></pre></td><td class="code"><pre><span class="line"><span class="selector-tag">button</span> {</span><br><span class="line">  <span class="attribute">animation</span>: throttle <span class="number">2s</span> step-end forwards;</span><br><span class="line">}</span><br><span class="line"><span class="selector-tag">button</span><span class="selector-pseudo">:active</span> {</span><br><span class="line">  <span class="attribute">animation</span>: none;</span><br><span class="line">}</span><br><span class="line"><span class="keyword">@keyframes</span> throttle {</span><br><span class="line">  <span class="selector-tag">from</span> {</span><br><span class="line">    <span class="attribute">pointer-events</span>: none;</span><br><span class="line">  }</span><br><span class="line">  <span class="selector-tag">to</span> {</span><br><span class="line">    <span class="attribute">pointer-events</span>: all;</span><br><span class="line">  }</span><br><span class="line">}</span><br></pre></td></tr></tbody></table>

你也可以查看以下任意链接：

*   [CSS throttle (codepen.io)](https://link.juejin.cn/?target=https://codepen.io/xboxyan/pen/rNKmmVq "https://codepen.io/xboxyan/pen/rNKmmVq")
*   [CSS throttle (runjs.work)](https://link.juejin.cn/?target=https://runjs.work/projects/47885939389440f4 "https://runjs.work/projects/47885939389440f4")

[](about:blank#%E4%B8%89%E3%80%81CSS-%E5%AE%9E%E7%8E%B0%E7%9A%84%E5%85%B6%E4%BB%96%E6%80%9D%E8%B7%AF "三、CSS 实现的其他思路")三、CSS 实现的其他思路
----------------------------------------------------------------------------------------------------------------------------------

还记得之前这一篇文章吗？

> [还在用定时器吗？借助 CSS 来监听事件](https://juejin.cn/post/7143051955810598926 "https://juejin.cn/post/7143051955810598926")

借用这种思路，也可以很轻松的实现节流的效果。而且为了更好的体验，可以用上真正的按钮禁用

<table><tbody><tr><td class="gutter"><pre><span class="line">1</span><br></pre></td><td class="code"><pre><span class="line">btn.<span class="property">disabled</span> = <span class="literal">true</span>;</span><br></pre></td></tr></tbody></table>

具体思路是这样的，通过`:active`去触发`transition`变化，然后通过监听`transition`回调去动态设置按钮的禁用状态，实现如下

定义一个无关紧要的过渡属性，比如`opacity`

<table><tbody><tr><td class="gutter"><pre><span class="line">1</span><br><span class="line">2</span><br><span class="line">3</span><br><span class="line">4</span><br><span class="line">5</span><br><span class="line">6</span><br><span class="line">7</span><br><span class="line">8</span><br></pre></td><td class="code"><pre><span class="line"><span class="selector-tag">button</span> {</span><br><span class="line">  <span class="attribute">opacity</span>: <span class="number">0.99</span>;</span><br><span class="line">  <span class="attribute">transition</span>: opacity <span class="number">2s</span>;</span><br><span class="line">}</span><br><span class="line"><span class="selector-tag">button</span><span class="selector-pseudo">:not</span>(<span class="selector-pseudo">:disabled</span>)<span class="selector-pseudo">:active</span> {</span><br><span class="line">  <span class="attribute">opacity</span>: <span class="number">1</span>;</span><br><span class="line">  <span class="attribute">transition</span>: <span class="number">0s</span>;</span><br><span class="line">}</span><br></pre></td></tr></tbody></table>

然后监听`transition`的起始回调

<table><tbody><tr><td class="gutter"><pre><span class="line">1</span><br><span class="line">2</span><br><span class="line">3</span><br><span class="line">4</span><br><span class="line">5</span><br><span class="line">6</span><br><span class="line">7</span><br><span class="line">8</span><br></pre></td><td class="code"><pre><span class="line"><span class="comment">// 过渡开始</span></span><br><span class="line"><span class="variable language_">document</span>.<span class="title function_">addEventListener</span>(<span class="string">"transitionstart"</span>, <span class="keyword">function</span> (<span class="params">ev</span>) {</span><br><span class="line">  ev.<span class="property">target</span>.<span class="property">disabled</span> = <span class="literal">true</span>;</span><br><span class="line">});</span><br><span class="line"><span class="comment">// 过渡结束</span></span><br><span class="line"><span class="variable language_">document</span>.<span class="title function_">addEventListener</span>(<span class="string">"transitionend"</span>, <span class="keyword">function</span> (<span class="params">ev</span>) {</span><br><span class="line">  ev.<span class="property">target</span>.<span class="property">disabled</span> = <span class="literal">false</span>;</span><br><span class="line">});</span><br></pre></td></tr></tbody></table>

这样做的最大好处是，**这部分禁用的逻辑是完全和业务逻辑是解耦的**，可以在任意时候，任意场合下无缝接入，也不受框架和环境影响，效果如下

![Kapture 2022-11-14 at 17.25.49](data:image/gif;base64,R0lGODlhAQABAIAAAAAAAP///yH5BAEAAAAALAAAAAABAAEAAAIBRAA7)

完整代码也可以查看以下任意链接：

*   [CSS throttle disabled (codepen.io)](https://link.juejin.cn/?target=https://codepen.io/xboxyan/pen/oNyWwvB "https://codepen.io/xboxyan/pen/oNyWwvB")
*   [CSS throttle disabled (runjs.work)](https://link.juejin.cn/?target=https://runjs.work/projects/41e8b998624743fc "https://runjs.work/projects/41e8b998624743fc")

[](about:blank#%E5%9B%9B%E3%80%81%E6%80%BB%E7%BB%93%E4%B8%80%E4%B8%8B "四、总结一下")四、总结一下
-------------------------------------------------------------------------------------

以上通过 CSS 的思路实现了类似“节流”的功能，相比 JS 实现而言，实现更精简、使用更简单，没有框架限制，下面一起总结一下实现要点：

1.  函数节流是一个非常常见的优化方式，可以有效避免函数过于频繁的执行
2.  CSS 的实现思路和 JS 不同，重点在于在于找到和该场景相关联的属性
3.  CSS 实现“节流”其实就是控制一个动画的精准控制，假设有一个动画控制按钮从**禁用**\->**可点击**的变化，每次点击时让这个动画重新执行一遍，在执行的过程中，一直处于**禁用**状态，这样就达到了“节流”的效果
4.  还可以通过 transition 的回调函数动态设置按钮禁用态
5.  这种实现的好处在于禁用逻辑和业务逻辑是完全解耦的

不过，这种实现方式还是比较有局限的，仅限于点击行为，像很多时候，节流可能会用在滚动事件或者键盘事件上，像这些场景就用传统方式实现就行了。最后，如果觉得还不错，对你有帮助的话，欢迎点赞、收藏、转发 ❤❤❤
