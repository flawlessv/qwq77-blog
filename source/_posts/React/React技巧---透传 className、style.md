---
title: React技巧---透传 className、style
tags:
  - React
---

### 透传 className、style
------------------

我们可以给组件设置 className 和 style：

```
import './App.css';
import { Button } from 'antd';

function App() {
  return (
    <div className="App">
        <Button className="aaa bbb" style={{
          width: '100px',
          height: '50px'
        }} type="primary">测试</Button>
    </div>
  );
}

export default App;

```

在页面里打开 DevTools 可以看到 className 和 style 都被设置到了 button 上。

![](https://p9-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/06c9dffdb6924b0da41188e8b2bf1516~tplv-k3u1fbpfcp-zoom-in-crop-mark:3024:0:0:0.image?)

这种功能的实现就是透传 className 和 style 的 props。

基本 antd 所有的组件都会做这个。

### 比如VisualList 组件的源码：

![](https://p9-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/6b8e4ff7e27c41e8a7ea00565717cf20~tplv-k3u1fbpfcp-zoom-in-crop-mark:3024:0:0:0.image?)

它取了传入的 className、style 的 props，还有剩余的所有 props。

对 className 做了一些处理，添加了两个 className：

![](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/b04ece79c12f41ab915210d5bc7d41ff~tplv-k3u1fbpfcp-zoom-in-crop-mark:3024:0:0:0.image?)

对 style 也做了扩展，添加了个 position: relative 的样式。

![](https://p1-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/f9722b0a20cb4937a3cc8deef5d8423b~tplv-k3u1fbpfcp-zoom-in-crop-mark:3024:0:0:0.image?)

然后把 style、className，额外的 props 都设置给最外层的 div。

这样，使用这个组件的时候，就可以自己定义一些样式，设置一些 props。

其中，classnames 是用来动态产生 className 的一个包，用起来很简单。

比如这样调用：

```
classNames('aaa', { bbb: true, ccc: false }, false, { eee: true }); 

```

那么最终的 className 就是 'aaa bbb eee'。

这样，组件用起来体验就和 html 标签差不多，可以自己控制一些样式。

这样写 props 的类型的时候，也是直接用了 html 标签的类型。

比如这个 List 的参数就继承了 React.HTMLArrtibutes<any>，也就是任意 html 标签的属性：

![](https://p1-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/92fd9f09cb7e455a9010a2c20b284ea5~tplv-k3u1fbpfcp-zoom-in-crop-mark:3024:0:0:0.image?)

当然，children 属性是不可以设置的。因为 React 用 children 参数来传递子组件。

比如 form 组件：

它的参数是继承了 React.FormHTMLAttributes<HTMLFormElement>：

![](https://p9-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/67849870d1f641308a9769a4bf895ab6~tplv-k3u1fbpfcp-zoom-in-crop-mark:3024:0:0:0.image?)

去掉了 children 和 onSubmit 这俩属性，因为这俩是 From 组件的参数。
### 总结
也就是说：**antd 的组件基本都支持传入 className、style 或者任何 html 标签的 props，会透传 props 到组件内的容器标签，所以用起来体验和原生标签很类似。但这也要求 props 实现 React.FormHTMLAttributes 的 type。**

