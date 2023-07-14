---
title: React技巧---通过forwardRef暴露一些方法
tags:
  - React
---

### 通过 forwardRef 暴露一些方法
--------------------

外界控制组件的方式就是通过传 props，但有时候想调用组件的一些方法呢？

这时候就需要 ref 了。

我们先来试一下 ref：

![](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/44f1ec8a3d5841b48f59d49363bd2f2e~tplv-k3u1fbpfcp-zoom-in-crop-mark:3024:0:0:0.image?)

通过 useRef 创建个 ref 对象，然后把 input 标签设置到 ref。

在 useEffect 里就可以调用 input 的方法了：

![](https://p9-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/1a1164d23a6b401a8e55186528a2acf4~tplv-k3u1fbpfcp-zoom-in-crop-mark:3024:0:0:0.image?)

### 但这是原生标签，如果是组件呢？

这时候就需要 forwardRef 了，也就是把组件内的 ref 转发一下。

比如这样：

```
import './App.css';
import { useRef } from 'react';
import { useEffect } from 'react';
import React from 'react';

const Guang: React.ForwardRefRenderFunction<HTMLInputElement> = (props, ref) => {
  return <div>
    <input ref={ref}></input>
  </div>
}

const WrapedGuang = React.forwardRef(Guang);

function App() {
  const ref = useRef<HTMLInputElement>(null);
 
  useEffect(()=> {
    console.log('ref', ref.current)
    ref.current?.focus()
  }, []);

  return (
    <div className="App">
      <WrapedGuang ref={ref}/>
    </div>
  );
}

export default App;

```

其实 forwardRef 这个 api 做的事情也很容易懂。

就是把 ref 转发到组件内部来设置：

![](https://p1-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/7102c90ebd7e4f1da3da7ee2401f3850~tplv-k3u1fbpfcp-zoom-in-crop-mark:3024:0:0:0.image?)

这样就把组件内的 input 通过 ref 的方式传递到了组件外。

效果和之前一样：

![](https://p6-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/4752b25fec3e4ca18834bc8e6090a169~tplv-k3u1fbpfcp-zoom-in-crop-mark:3024:0:0:0.image?)

不过被 forwardRef 包裹的组件的类型就要用 React.forwardRefRenderFunction 了：

![](https://p6-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/cc27ede261f143fa80038a90b924917f~tplv-k3u1fbpfcp-zoom-in-crop-mark:3024:0:0:0.image?)

第一个类型参数是 ref 的 content 的类型。
### useImperativeHandle
但有的时候，我不是想把原生标签暴露出去，而是暴露一些自定义方法。

这时候就需要 useImperativeHandle 的 hook 了。

这样写：

```
import './App.css';
import { useRef } from 'react';
import { useEffect } from 'react';
import React from 'react';
import { useImperativeHandle } from 'react';

interface RefProps {
  aaa: () => void;
}

const Guang: React.ForwardRefRenderFunction<RefProps> = (props, ref) => {
  const inputRef = useRef<HTMLInputElement>(null);

  useImperativeHandle(ref, () => {
    return {
      aaa() {
        inputRef.current?.focus();
      }
    }
  });

  return <div>
    <input ref={inputRef}></input>
  </div>
}

const WrapedGuang = React.forwardRef(Guang);

function App() {
  const ref = useRef<RefProps>(null);
 
  useEffect(()=> {
    console.log('ref', ref.current)
    ref.current?.aaa();
  }, []);

  return (
    <div className="App">
      <WrapedGuang ref={ref}/>
    </div>
  );
}

export default App;

```

也就是用 useImperativeHanlde 自定义了 ref 对象：

![](https://p6-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/ce6b81cd481c4e2b82b66aa477196b39~tplv-k3u1fbpfcp-zoom-in-crop-mark:3024:0:0:0.image?)
### 总结

**React 可以用 ref 保存原生标签，通过 ref.current 调用这个对象的属性、方法。跨组件传递 ref 需要用 forwardRef 方法，如果你要进一步自定义 ref，那就要用 useImperativeHandle 的 hook。**

然后看看 antd 组件是怎么用 ref 的。

就如说 VisualList 组件：

![](https://p1-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/dfaf6bd2223a4a37b0712dc816ca2f2f~tplv-k3u1fbpfcp-zoom-in-crop-mark:3024:0:0:0.image?)

它也是包了一层 React.forwardRef，内部用 useImperativeHandle 自定义了 ref：

![](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/17f6a3e4543547439346a51046c2afb3~tplv-k3u1fbpfcp-zoom-in-crop-mark:3024:0:0:0.image?)

这样外部就可以调用这个 ref 的方法了：

![](https://p1-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/82f4f864fe9843a89249988185edd63f~tplv-k3u1fbpfcp-zoom-in-crop-mark:3024:0:0:0.image?)

再比如 Form 组件：

它也是被 forwarRef 包裹的函数组件：

![](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/c9614eadd5cd4b519b88d3b828600983~tplv-k3u1fbpfcp-zoom-in-crop-mark:3024:0:0:0.image?)

内部用 useImperativeHandle 返回了自定义的对象：

![](https://p6-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/82b288e20c6e4b609bea70073a85461d~tplv-k3u1fbpfcp-zoom-in-crop-mark:3024:0:0:0.image?)

所以你才可以这样调用 form 组件的方法：

![](https://p9-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/c05f9f0ff5654d76949468ac84427fff~tplv-k3u1fbpfcp-zoom-in-crop-mark:3024:0:0:0.image?)

这就是说：**antd 的组件都会用 forwardRef 包裹一层，用来转发 ref，或者是转发内部的 html 标签的引用，或者是用 useImperativeHandle 自定义 ref 对象，来暴露一些方法。**

