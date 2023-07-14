---
title: React技巧---用Context来跨组件传递值
tags:
  - React
---

### 用 Context 来跨组件传递值
-----------------

antd 里很多配置的传递都是通过 Context。

比如 disabled 的设置：

![](https://p1-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/c0b197ccc53048ea9bfdc0fe6bad7d64~tplv-k3u1fbpfcp-zoom-in-crop-mark:3024:0:0:0.image?)

通过 React.createContext 创建 context 对象，通过 Provider 修改 context 的值。

在最外层包裹这个 Provider 组件来修改 context 值：

![](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/10de18d17ac945278758c83d8440357f~tplv-k3u1fbpfcp-zoom-in-crop-mark:3024:0:0:0.image?)

然后你可以在任意的组件把 context 值取出来用：

![](https://p9-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/893acaa56cba412db2f40d8659178362~tplv-k3u1fbpfcp-zoom-in-crop-mark:3024:0:0:0.image?)

![](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/23bf4baf91824aac99f9a29ca199782b~tplv-k3u1fbpfcp-zoom-in-crop-mark:3024:0:0:0.image?)

像什么主题、大小等配置，都是通过 Context 传递的。

除了用来传递配置外，很多组件也依赖 Context 来传递一些值，比如 Form：

![](https://p9-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/64dfcdeac2e44374b332b668a7585e20~tplv-k3u1fbpfcp-zoom-in-crop-mark:3024:0:0:0.image?)

### Form 组件使用context
在 Form 组件里设置 form 对象，然后 setFieldValue 设置字段值。

为什么 Form.Item 里加个 name 就可以取出来了呢？

我并没有传递 form 参数过去呀？

很明显，这里也是用 Context 来传递的：

antd 会创建这样一个 context 对象：

![](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/2af7961a416e496993d6f1a58e8843ca~tplv-k3u1fbpfcp-zoom-in-crop-mark:3024:0:0:0.image?)

然后在外层用 Provider 设置 context 值：

![](https://p9-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/452b0337bac54aa59b3290436bcc2494~tplv-k3u1fbpfcp-zoom-in-crop-mark:3024:0:0:0.image?)

也就是我们这里传的 form：

![](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/ae89efc7022e4c23ac9e14600a8de739~tplv-k3u1fbpfcp-zoom-in-crop-mark:3024:0:0:0.image?)

那 Form.Item 里自然可以拿到 context 的值，从而取到具体字段信息了：

![](https://p9-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/5d3f17b8dc814cdf96b7b1c711e04d15~tplv-k3u1fbpfcp-zoom-in-crop-mark:3024:0:0:0.image?)

![](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/79ea02731d224ee5bb3c83bf031751de~tplv-k3u1fbpfcp-zoom-in-crop-mark:3024:0:0:0.image?)
### 总结
也就是说：**antd 里大量用到了 Context，除了用来传递 config、theme、size 等全局配置信息外，还用来跨组件传递数据，比如 Form、Form.Item 组件，就是通过 Provider、useContext 来存取值的。**

