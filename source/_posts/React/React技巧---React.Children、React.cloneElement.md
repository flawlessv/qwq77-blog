---
title: React技巧---React.Children、React.cloneElement
tags:
  - React
---


### React.Children、React.cloneElement
---------------------------------

React 组件可以设置内容，在组件内通过 props.children 来取。

```
import React from 'react';

interface GuangProps {
  children: React.ReactNode[];
}

const Guang: React.FunctionComponent<GuangProps> = (props) => {
  console.log(props);
  return <div className="guang">
    {props.children}
  </div>
}

function App() {
  return (
    <div className="App">
      <Guang>
        <p>111</p>
        <p>222</p>
      </Guang>
    </div>
  );
}

export default App;

```

比如我在组件里把 props.children 取出来，放到 className 为 guang 的 div 下：

![](https://p1-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/502415a479cd4292b4bfa9dfdaa00a35~tplv-k3u1fbpfcp-zoom-in-crop-mark:3024:0:0:0.image?)

![](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/3ea887f231ab4f2485f5b4e14a9f0d8a~tplv-k3u1fbpfcp-zoom-in-crop-mark:3024:0:0:0.image?)

如果想对这些 children 做一些操作，就需要用 React.Children 的 api 了，比如 React.Children.toArray、React.Children.forEach、React.Children.map

有同学说，props.children 本来就是数组啊，直接操作不就行了？

不行的，直接操作有一些问题，比如我 sort 一下：

![](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/9b98135f12c64294aac3d20a3fdcaf36~tplv-k3u1fbpfcp-zoom-in-crop-mark:3024:0:0:0.image?)

会报错：

![](https://p1-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/af043aec5d6441289cc568bce5faf569~tplv-k3u1fbpfcp-zoom-in-crop-mark:3024:0:0:0.image?)

所以 props.children 不能直接当做数组用，需要 toArray 一下：

![](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/e63384d02fdf44889788e923e7f4f784~tplv-k3u1fbpfcp-zoom-in-crop-mark:3024:0:0:0.image?)

这样就没有报错了：

![](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/8c0aad97adba4ac8bb6677187b920adf~tplv-k3u1fbpfcp-zoom-in-crop-mark:3024:0:0:0.image?)

同理，React.Children 的 forEach 和 map 也很容易理解。

而且还可以用 React.cloneElement 复制下传入的 ReactElement。

比如这样：

![](https://p9-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/6ff7c16f3c8d45379ee74793611aad4c~tplv-k3u1fbpfcp-zoom-in-crop-mark:3024:0:0:0.image?)

用 React.Children.map 遍历 children，对每个 child 复制一份出来，修改下 props ，并且添加一个 children。

效果是这样的：

![](https://p6-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/7c4f6a9e988348e8b7a31f6287d97127~tplv-k3u1fbpfcp-zoom-in-crop-mark:3024:0:0:0.image?)
### React.cloneElement
React.cloneElement 的第二个参数是修改的 props，后面的参数是 children：

![](https://p6-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/f267a0cd9180419c9991eff035093954~tplv-k3u1fbpfcp-zoom-in-crop-mark:3024:0:0:0.image?)

结合 React.Children 的 api 和 React.cloneElement 的 api 就可以任意修改 children 渲染的结果。

在 antd 里也有大量运用：

比如 button 组件里，通过 map + cloneElement 来处理中文字符的问题：

![](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/582497b5b98847ab9df0209dd8ab31a7~tplv-k3u1fbpfcp-zoom-in-crop-mark:3024:0:0:0.image?)

或者用 map + cloneElement 给 child 的 children 外包一层组件：

![](https://p6-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/148430daa9634da4afe679401a4d55bc~tplv-k3u1fbpfcp-zoom-in-crop-mark:3024:0:0:0.image?)

更巧妙的是 VirtualList 里的应用：

![](https://p6-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/6f260997587f44789837ff89e27c8040~tplv-k3u1fbpfcp-zoom-in-crop-mark:3024:0:0:0.image?)

你不需要给传入的 children 设置 ref，antd 会通过 map + cloneElement 给你加上 ref 的 props，然后在回调函数里把这个 ref 保存下来。

这样就拿到了你传入的每一个 children 的 ref。

比如根据 key 来保存每个 Item 的 ref：

![](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/46123f5a843c4c499607c445fb8e6fa6~tplv-k3u1fbpfcp-zoom-in-crop-mark:3024:0:0:0.image?)
### 总结
也就是说：**antd 组件里大量用到了 React.Children + React.cloneElement 的 api 对 props.children 做一些修改，比如包一层组件、添加 ref 等参数、添加一些 children 等。**