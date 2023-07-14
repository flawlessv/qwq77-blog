---
title: React技巧---通过useCallback、useMemo性能优化
tags:
  - React
  - 性能优化
---


### useCallback、useMemo
-------------------

useMemo 和 useCallback 是性能优化相关的 hook。

很多人不知道啥时候用，其实看下 antd 怎么用的就知道了：

![](https://p1-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/8426f36868e24f50a15c839a4ffbf2b9~tplv-k3u1fbpfcp-zoom-in-crop-mark:3024:0:0:0.image?)

比如 VisualList 组件里计算 start、end、scrollHeight 这些值需要大量的计算。

这些计算需要每次 render 都跑一遍么？

不需要，只有在某些值变化的时候才需要重新计算。

这时候用 React.useMemo 包裹就可以减少计算量，它只会在 deps 数组变化的时候执行第一个参数的函数。

useMemo 是 deps 变化之后重新执行函数创建值，而 useCallback 并不会执行函数，它只是在 deps 变化的时候返回第一个参数的函数：

![](https://p6-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/87cb5b426ccd4fe98837527d368c5493~tplv-k3u1fbpfcp-zoom-in-crop-mark:3024:0:0:0.image?)

### 这样有什么用呢？

react 重新渲染的依据是 props 是否有变化，如果每次都创建新的函数，那是不是每次都会重新渲染？

所以用 useCallback 包裹的函数参数，就可以在 deps 没变的时候，始终返回同一个函数，这样避免了没必要的渲染。

当然，useMemo 也有这个作用：

比如说 Form 组件源码里的这个 useMemo：

![](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/0765bfbaef7049d68d4d9ab81e99b8c6~tplv-k3u1fbpfcp-zoom-in-crop-mark:3024:0:0:0.image?)

你说它是为了减少计算量么？

并不是，它没有做任何计算，只是把参数原封不动返回了。

这也同样是为了避免 props 变化。
### 总结
也就是说：**antd 里很多地方都用了 useMemo 和 useCallback 来进行渲染性能优化。useMemo 只有在 deps 数组变化的时候才会执行第一个函数，返回新的值，可以用来减少不必要的计算，也可以保证 props 不变来避免不要的渲染。useCallback 是只有 deps 数组变化的时候才返回第一个函数的值，可以保证 props 不变来用来避免不必要的渲染**

