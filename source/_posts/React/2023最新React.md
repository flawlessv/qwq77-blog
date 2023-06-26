---
title: 2023最新React
tags:
  - React
  -
---

**源码分析**

![image.png](https://p6-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/4dd8591ea2c74360b6a64719b6103552~tplv-k3u1fbpfcp-zoom-in-crop-mark:3024:0:0:0.image?)

## 一、React18 有哪些更新？

[juejin.cn/post/709403…](https://juejin.cn/post/7094037148088664078#heading-12 "https://juejin.cn/post/7094037148088664078#heading-12")

1.  setState 自动批处理

在 react17 中，只有 react 事件会进行批处理，原生 js 事件、promise，setTimeout、setInterval 不会

react18，将所有事件都进行批处理，即多次 setState 会被合并为 1 次执行，提高了性能，在数据层，将多个状态更新合并成一次处理（在视图层，将多次渲染合并成一次渲染）

2.  引入了新的 root API，支持 new concurrent renderer(并发模式的渲染)

```
//React 17
import React from "react"
import ReactDOM from "react-dom"
import App from "./App"

const root = document.getElementById("root")
ReactDOM.render(<App/>,root)

// 卸载组件
ReactDOM.unmountComponentAtNode(root)

// React 18
import React from "react"
import ReactDOM from "react-dom/client"
import App from "./App"
const root = document.getElementById("root")
ReactDOM.createRoot(root).render(<App/>)

// 卸载组件
root.unmount()

```

3.  去掉了对 IE 浏览器的支持，react18 引入的新特性全部基于现代浏览器，如需支持需要退回到 react17 版本
4.  flushSync

批量更新是一个破坏性的更新，如果想退出批量更新，可以使用 flushSync

```
import React,{useState} from "react"
import {flushSync} from "react-dom"

const App=()=>{
  const [count,setCount]=useState(0)
  const [count2,setCount2]=useState(0)

  return (
    <div className="App">
      <button onClick=(()=>{
        // 第一次更新
        flushSync(()=>{
          setCount(count=>count+1)
        })
        // 第二次更新
        flushSync(()=>{
          setCount2(count2=>count2+1)
        })
      })>点击</button>
      <span>count:{count}</span>
      <span>count2:{count2}</span>
    </div>
  )
}
export default App


```

5.  react 组件返回值更新

- 在 react17 中，返回空组件只能返回 null，显式返回 undefined 会报错
- 在 react18 中，支持 null 和 undefined 返回

6.  strict mode 更新

当你使用严格模式时，React 会对每个组件返回两次渲染，以便你观察一些意想不到的结果,在 react17 中去掉了一次渲染的控制台日志，以便让日志容易阅读。react18 取消了这个限制，第二次渲染会以浅灰色出现在控制台日志

6.  Suspense 不再需要 fallback 捕获
7.  支持 useId

在服务器和客户端生成相同的唯一一个 id，避免 hydrating 的不兼容

8.  useSyncExternalStore

用于解决外部数据撕裂问题

9.  useInsertionEffect

这个 hooks 只建议在 css in js 库中使用，这个 hooks 执行时机在 DOM 生成之后，useLayoutEffect 执行之前，它的工作原理大致与 useLayoutEffect 相同，此时无法访问 DOM 节点的引用，一般用于提前注入脚本

10. **Concurrent Mode**

并发模式不是一个功能，而是一个底层设计。

它可以帮助应用保持响应，根据用户的设备性能和网速进行调整，它通过渲染可中断来修复阻塞渲染机制。在**concurrent 模式**中，React 可以同时更新多个状态

区别就是使**同步不可中断更新**变成了**异步可中断更新**

useDeferredValue 和 startTransition 用来标记一次非紧急更新

## 二、React 的设计思想

- **组件化**

每个组件都符合开放-封闭原则，封闭是针对渲染工作流来说的，指的是组件内部的状态都由自身维护，只处理内部的渲染逻辑。开放是针对组件通信来说的，指的是不同组件可以通过 props（单项数据流）进行数据交互

- **数据驱动视图**

UI=f(data)

通过上面这个公式得出，如果要渲染界面，不应该直接操作 DOM，而是通过修改数据(state 或 prop)，数据驱动视图更新

- **虚拟 DOM**

由浏览器的渲染流水线可知，DOM 操作是一个昂贵的操作，很耗性能，因此产生了虚拟 DOM。虚拟 DOM 是对真实 DOM 的映射，React 通过新旧虚拟 DOM 对比，得到需要更新的部分，实现数据的增量更新

[React 设计模式](https://juejin.cn/post/7007214462813863950 "https://juejin.cn/post/7007214462813863950")

## 三、JSX 是什么，它和 JS 有什么区别

JSX 是 react 的语法糖，它允许在 html 中写 JS，它不能被浏览器直接识别，需要通过 webpack、babel 之类的编译工具转换为 JS 执行

JSX 与 JS 的区别：

1.  JS 可以被打包工具直接编译，不需要额外转换，jsx 需要通过 babel 编译，它是 React.createElement 的语法糖，使用 jsx 等价于 React.createElement
2.  jsx 是 js 的语法扩展，允许在 html 中写 JS；JS 是原生写法，需要通过 script 标签引入

**为什么在文件中没有使用 react，也要在文件顶部 import React from “react”**

只要使用了 jsx，就需要引用 react，因为 jsx 本质就是 React.createElement

**为什么 React 自定义组件首字母要大写**

jsx 通过 babel 转义时，调用了 React.createElement 函数，它接收三个参数，分别是 type 元素类型，props 元素属性，children 子元素。

如下图所示，从 jsx 到真实 DOM 需要经历*jsx->虚拟 DOM->真实 DOM*。如果组件首字母为小写，它会被当成字符串进行传递，在创建虚拟 DOM 的时候，就会把它当成一个 html 标签，而 html 没有 app 这个标签，就会报错。组件首字母为大写，它会当成一个变量进行传递，React 知道它是个自定义组件就不会报错了

```
<app>lyllovelemon</app>
// 转义后
React.createElement("app",null,"lyllovelemon")

<App>lyllovelemon</App>
// 转义后
React.createElement(App,null,lyllovelemon)

```

---

**React 组件为什么不能返回多个元素**

这个问题也可以理解为 React 组件为什么只能有一个根元素，原因：

1.  React 组件最后会编译为 render 函数，函数的返回值只能是 1 个，如果不用单独的根节点包裹，就会并列返回多个值，这在 js 中是不允许的

```
class App extends React.Component{
  render(){
    return(
    <div>
     <h1 className="title">lyllovelemon</h1>
      <span>内容</span>
    </div>
  )
}

//编译后
class App extends React.Component{
  render(){
    return React.createElement('div',null,[
      React.createElement('h1',{className:'title'},'lyllovelemon'),
      React.createElement('span'),null,'内容'
      ])
  }
}

```

2.  react 的虚拟 DOM 是一个树状结构，树的根节点只能是 1 个，如果有多个根节点，无法确认是在哪棵树上进行更新

vue 的根节点为什么只有一个也是同样的原因

React 组件怎样可以返回多个组件

- 使用 HOC（高阶函数）
- 使用 React.Fragment,可以让你将元素列表加到一个分组中，而且不会创建额外的节点（类似 vue 的 template)

```
renderList(){
  this.state.list.map((item,key)=>{
    return (<React.Fragment>
      <tr key={item.id}>
        <td>{item.name}</td>
        <td>{item.age}</td>
        <td>{item.address}</td>
      </tr>
    </React.Fragment>)
  })
}

```

3.  使用数组返回

```
renderList(){
  this.state.list.map((item,key)=>{
    return [
      <tr key={item.id}>
        <td>{item.name}</td>
        <td>{item.age}</td>
        <td>{item.address}</td>
      </tr>
    ]
  })
}

```

**React 中元素和组件的区别**

react 组件有类组件、函数组件

react 元素是通过 jsx 创建的

```
const element = <div className="element">我是元素</div>

```

## 四、简述 React 的生命周期

生命周期指的是组件实例从创建到销毁的流程，函数组件没有生命周期，只有类组件才有，因为只有 class 组件会创建组件实例

组件的生命周期可以分为**挂载、更新、卸载**阶段

**挂载**

**constructor** 可以进行 state 和 props 的初始化

static getDerivedStateFromProps

render

**componentDidMount** 第一次渲染后调用，可以访问 DOM，进行异步请求和定时器、消息订阅

**更新**

当组件的 props 或 state 变化会触发更新

static getDerivedStateFromProps

**shouldComponentUpdate** 返回一个布尔值，默认返回 true，可以通过这个生命周期钩子进行性能优化，确认不需要更新组件时调用

render

getSnapShotBeforeUpdate

componentDidUpdate 在组件完成更新后调用

**卸载**

componentWillUnmount 组件从 DOM 中被移除的时候调用

**错误捕获**

static getDerivedStateFromError 在 errorBoundary 中使用

componentDidCatch

**render**是 class 组件中唯一必须实现的方法

## 五、React 事件机制

**什么是合成事件**

**React 基于浏览器的事件机制实现了一套自身的事件机制，它符合 W3C 规范，包括事件触发、事件冒泡、事件捕获、事件合成和事件派发等**

React 事件的设计动机(作用)：

- **在底层磨平不同浏览器的差异，React 实现了统一的事件机制，我们不再需要处理浏览器事件机制方面的兼容问题，在上层面向开发者暴露稳定、统一的、与原生事件相同的事件接口**
- **React 把握了事件机制的主动权，实现了对所有事件的中心化管控**
- **React 引入事件池避免垃圾回收，在事件池中获取或释放事件对象，避免频繁的创建和销毁**

**React 事件机制和原生 DOM 事件流有什么区别**

**虽然合成事件不是原生 DOM 事件，但它包含了原生 DOM 事件的引用，可以通过 e.nativeEvent 访问**

---

**DOM 事件流是怎么工作的**，一个页面往往会绑定多个事件，页面接收事件的顺序叫事件流

W3C 标准事件的传播过程：

1.  事件捕获
2.  处于目标
3.  事件冒泡

常用的事件处理性能优化手段：**事件委托**

**把多个子元素同一类型的监听函数合并到父元素上，通过一个函数监听的行为叫事件委托**

**我们写的 React 事件是绑定在 DOM 上吗，如果不是绑定在哪里**

React16 的事件绑定在 document 上， React17 以后事件绑定在 container 上,**ReactDOM.render(app,container)**

**React 事件机制**总结如下：

事件绑定 事件触发

- **React 所有的事件绑定在 container 上**(react17 以后),而不是绑定在 DOM 元素上（作用：减少内存开销，所有的事件处理都在 container 上，其他节点没有绑定事件）
- React 自身实现了一套冒泡机制，不能通过 return false 阻止冒泡
- React 通过**SytheticEvent**实现了**事件合成**

![](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/6ad1c0b6ee9c42578b6fc7b46a3a2e39~tplv-k3u1fbpfcp-zoom-in-crop-mark:3024:0:0:0.image)

**React 实现事件绑定的过程**

**1.建立合成事件与原生事件的对应关系**

**registrationNameModule,** 它建立了 React 事件到 plugin 的映射，它包含 React 支持的所有事件的类型，用于判断一个组件的 prop 是否是事件类型

```
{
   onBlur:SimpleEventPlugin,
   onClick:SimpleEventPlugin,
   onClickCapture:SimpleEventPlugin,
   onChange:ChangeEventPlugin,
   onChangeCapture:ChangeEventPlugin,
   onMouseEnter:EnterLeaveEventPlugin,
   onMouseLeave:EnterLeaveEventPlugin,
   ...
}

```

**registrationNameDependencies，** 这个对象记录了 React 事件到原生事件的映射

```
{
  onBlur: ['blur'],
  onClick: ['click'],
  onClickCapture: ['click'],
  onChange: ['blur', 'change', 'click', 'focus', 'input', 'keydown', 'keyup', 'selectionchange'],
  onMouseEnter: ['mouseout', 'mouseover'],
  onMouseLeave: ['mouseout', 'mouseover'],
}

```

**plugins 对象,** 记录了所有注册的插件列表

```
plugins = [LegacySimpleEventPlugin, LegacyEnterLeaveEventPlugin, ...]

```

---

**为什么针对同一个事件，即使可能存在多次回调，document（container）也只需要注册一次监听**

因为 React 注册到 document(container)上的并不是一个某个 DOM 节点具体的回调逻辑，而是一个统一的事件分发函数 dispatchEvent - > 事件委托思想

**dispatchEvent 是怎么实现事件分发的**

事件触发的本质是对 dispatchEvent 函数的调用

![](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/2c8b7a2369a943118f865cb9369638b4~tplv-k3u1fbpfcp-zoom-in-crop-mark:3024:0:0:0.image)

**React 事件处理为什么要手动绑定 this**

react 组件会被编译为 React.createElement,在 createElement 中，它的 this 丢失了，并不是由组件实例调用的，因此需要手动绑定 this

为什么不能通过 return false 阻止事件的默认行为

因为 React 基于浏览器的事件机制实现了一套自己的事件机制，和原生 DOM 事件不同，它采用了事件委托的思想，通过 dispatch 统一分发事件处理函数

**React 怎么阻止事件冒泡**

- 阻止合成事件的冒泡用 e.stopPropagation()
- 阻止合成事件和最外层 document 事件冒泡，使用 e.nativeEvent.stopImmediatePropogation()
- 阻止合成事件和除了最外层 document 事件冒泡，通过判断 e.target 避免

```
document.body.addEventListener('click',e=>{
  if(e.target && e.target.matches('div.stop')){
    return
  }
  this.setState({active:false})
})

```

HOC 和 hooks 的区别

useEffect 和 useLayoutEffect 区别

**React 性能优化手段**

1.  shouldComponentUpdate
2.  memo
3.  getDerviedStateFromProps
4.  使用 Fragment
5.  v-for 使用正确的 key
6.  拆分尽可能小的可复用组件，ErrorBoundary
7.  使用 React.lazy 和 React.Suspense 延迟加载不需要立马使用的组件

## 六、常用组件

**错误边界**

React 部分组件的错误不应该导致整个应用崩溃，为了解决这个问题，React16 引入了错误边界

使用方法：

React 组件在内部定义了 getDerivedStateFromError 或者 componentDidCatch，它就是一个错误边界。getDerviedStateFromError 和 componentDidCatch 的区别是前者展示降级 UI，后者记录具体的错误信息，它只能用于 class 组件

```
import React from "react"
class ErrorBoundary extends React.Component{
  constructor(props){
    super(props)
    this.state={
      hasError:false
    }
  }
  staic getDerivedStateFromError(){
    return { hasError:true}
  }
  componentDidCatch(err,info){
    console.error(err,info)
  }
  render(){
    if(this.state.hasError){
      return <div>Oops,err</div>
    }
    return this.props.children
  }
}

// App.jsx
import React from "react"
import ErrorBoundary from "./components/ErrorBoundary"
import ComponentA from "./components/ComponentA"
export class App extends React.Component{
  render(){
    return (
      <ErrorBoundary>
        <ComponentA></ComponentA>
      </ErrorBoundary>
    )
  }
}

```

错误边界无法捕获自身的错误，也无法捕获事件处理、异步代码(setTimeout、requestAnimationFrame)、服务端渲染的错误

**Portal**

Portal 提供了让子组件渲染在除了父组件之外的 DOM 节点的方式,它接收两个参数，第一个是需要渲染的 React 元素，第二个是渲染的地方(DOM 元素)

```
ReactDOM.createPortal(child,container)

```

用途：弹窗、提示框等

[**Fragment**](https://link.juejin.cn/?target=https%3A%2F%2Fzh-hans.reactjs.org%2Fdocs%2Ffragments.html%23gatsby-focus-wrapper "https://zh-hans.reactjs.org/docs/fragments.html#gatsby-focus-wrapper")

Fragment 提供了一种将子列表分组又不产生额外 DOM 节点的方法

[**Context**](https://link.juejin.cn/?target=https%3A%2F%2Fzh-hans.reactjs.org%2Fdocs%2Fcontext.html%23gatsby-focus-wrapper "https://zh-hans.reactjs.org/docs/context.html#gatsby-focus-wrapper")

常规的组件数据传递是使用 props，当一个嵌套组件向另一个嵌套组件传递数据时，props 会被传递很多层，很多不需要用到 props 的组件也引入了数据，会造成数据来源不清晰，多余的变量定义等问题，Context 提供了一种跨层级组件数据传递的方法

```
const ThemeContext = React.createContext('light')
class App extends React.Component {
  render(){
    return(
      <ThemeContext.Provider value="dark">
        <ToolBar/>
      </ThemeContext>
    )
  }
}

function ToolBar(){
  return <div>
   <ThemeButton/>
  </div>
}

class ThemeButton extends React.Component {
  static contextType = ThemeContext
  render(){
    return <Button theme={this.context}></Button>
  }
}

```

[Suspense](https://link.juejin.cn/?target=https%3A%2F%2Fzh-hans.reactjs.org%2Fdocs%2Freact-api.html%23suspense "https://zh-hans.reactjs.org/docs/react-api.html#suspense")

Suspense 使组件允许在某些操作结束后再进行渲染，比如接口请求,一般与 React.lazy 一起使用

Transition

Transition 是 React18 引入的一个并发特性，允许操作被中断，避免回到可见内容的 Suspense 降级方案

## 七、Redux 工作原理

Redux 是一个状态管理库，使用场景：

- 跨层级组件数据共享与通信
- 一些需要持久化的全局数据，比如用户登录信息

![](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/1405ddf626f844da9f383cf54cbf8c8f~tplv-k3u1fbpfcp-zoom-in-crop-mark:3024:0:0:0.image)

Redux 工作原理

使用单例模式实现

Store 一个全局状态管理对象

Reducer 一个纯函数，根据旧 state 和 props 更新新 state

Action 改变状态的唯一方式是 dispatch action

## 八、React-Router 工作原理

##### 为什么需要前端路由

1.  早期：一个页面对应一个路由，路由跳转导致页面刷新，用户体验差
2.  ajax 的出现使得不刷新页面也可以更新页面内容，出现了*SPA*（单页应用）。*SPA*不能记住用户操作，只有一个页面对 URL 做映射，SEO 不友好
3.  前端路由帮助我们在仅有一个页面时记住用户进行了哪些操作

##### 前端路由解决了什么问题

1.  当用户刷新页面，浏览器会根据当前 URL 对资源进行重定向(发起请求)
2.  单页面对服务端来说就是一套资源，怎么做到不同的 URL 映射不同的视图内容
3.  拦截用户的刷新操作，避免不必要的资源请求；感知 URL 的变化

**react-router-dom 有哪些组件**

HashRouter/BrowserRouter 路由器

Route 路由匹配

Link 链接，在 html 中是个锚点

NavLink 当前活动链接

Switch 路由跳转

Redirect 路由重定向

```
<Link to="/home">Home</Link>
<NavLink to="/abount" activeClassName="active">About</NavLink>
<Redirect to="/dashboard">Dashboard</Redirect>

```

React Router 核心能力：**跳转**

**路由**负责定义路径和组件的映射关系

**导航**负责触发路由的改变  
路由器根据 Route 定义的映射关系为新的路径匹配对应的逻辑

**BrowserRouter**使用的**HTML5**的**history api**实现路由跳转  
**HashRoute**r 使用 URL 的**hash 属性**控制路由跳转

**前端通用路由解决方案**

- hash 模式

> 改变 URL 以#分割的路径字符串，让页面感知路由变化的一种模式,通过*hashchange*事件触发

- history 模式

> 通过浏览器的 history api 实现,通过*popState*事件触发

## 九、数据如何在 React 组件中流动

**React 组件通信**

**react 组件通信方式有哪些**

组件通信的方式有很多种，可以分为以下几种：

1.  父组件向子组件通信
2.  子组件向父组件通信
3.  兄弟组件通信
4.  父组件向后代组件通信
5.  无关组件通信

**父组件向子组件通信**

- **props 传递**，利用 React 单向数据流的思想，通过 props 传递

```
function Child(props){
  return (
    <div className="child">
     <input value={props.name} type="text"/>
    </div>
  )
}
const Parent = <Child name="我是儿子"/>

```

**子组件向父组件通信**

- **回调函数**

父组件向子组件传递一个函数，通过函数回调，拿到子组件传过来的值

```
import React from "react"
class Parent extends React.Component{
  constructor(){
    super()
    this.state={
      price:0
    }
  }
  getPrice(val){
    this.setState({
      price:val
    })
  }
  render(){
    return (<div>
      <span className="label">价格:</span>
      <span className="value">{this.state.price}</span>
      <Child getPrice={this.getPrice.bind(this)}/>
    </div>)
  }
}

class Child extends React.Component{
  getItemPrice(e){
    this.props.getPrice(e)
  }
  render(){
    return (
      <div>
        <button onClick={this.getItemPrice.bind(this)}>廓形大衣</button>
        <button onClick={this.getItemPrice.bind(this)>牛仔裤</button>
      </div>
    )
  }
}

```

- **事件冒泡**

点击子组件的 button 按钮，事件会冒泡到父组件上

```
const Child = () => {
    return <button>点击</button>;
};

const Parent = () => {
    const sayName = name => {
        console.log(name);
    };
    return (
        <div onClick={() => sayName('lyllovelemon')}>
            <Child />
        </div>
    );
};

export default Parent;

```

- **Ref**

```
import React from "react"
class Parent extends React.Component{
  constructor(props){
    super(props)
    this.myRef=React.createRef()
  }
  componentDidMount(){
    this.myRef.current.changeVal('lyllovelemon')
  }
}
class Child extends React.Component{
  constructor(props){
    super(props)
  }
  changeVal(name){
    console.log(name)
  }
  render(){
    return (<div></div>)
  }
}

```

**兄弟组件通信**

实际上就是通过父组件中转数据的，子组件 a 传递给父组件，父组件再传递给子组件 b

```
import React from "react"
class Parent extends React.Component{
  constructor(props){
    super(props)
    this.state={
      count:0
    }
  }
  increment(){
    this.setState({
      count:this.state.count+1
    })
  }
  render(){
    return (
      <div>
        <ChildOne count={this.state.count} />
        <ChildTwo onClick={this.increment} />
      </div>
    )
  }
}

```

**父组件向后代组件通信**

**Context**

```
import React from "react"
const PriceContext = React.createContext("price")
export default class Parent extends React.Component{
  constructor(props){
    super(props)
  }
  render(){
    return (
      <PriceContext.Provider value={200}>
      </PriceContext>
    )
  }
}
class Child extends React.Component{
  ...
}
class SubChild extends React.Component{
  constructor(props){
    super(props)
  }
  render(){
    return (
      <PriceContext.Consumer>
        { price=> <div>price:{price}</div> }
      </PriceContext.Consumner>
    )
  }
}

```

**HOC**

**Redux**

ref，useRef，forwardRef，useImperativeHandle

## 十、React Hooks

**React hooks 解决了什么问题**

在 React16.8 以前，常用的组件写法有 class 组件和 function 组件

```
class Demo extends React.Component{
    constructor(props){
        super(props)
        this.state={
            name:'lyllovelemon'
        }
    }
    changeName(){
        this.setState({
            name:'lylmusiclover'
        })
    }
    render(){
        return (
            <div>
                {this.state.name}
                <button onClick={this.changeName.bind(this)}>换名</button>
            </div>
        )
    }
}

function Demo2({name,setName}){
    return <div>
        {name}
        <button onClick={()=>setName('哈哈哈')}>换名</button>
    </div>
}

//App.jsx
function App() {
    const [name,setName]=useState('lyl')
  return (
    <div className="App">
        <Demo/>
        <Demo2 setName={setName} name={name}/>
    </div>
  )
}

```

_**函数组件与类组件的区别**_:

1.  类组件需要声明 constructor，函数组件不需要
2.  类组件需要手动绑定 this，函数组件不需要
3.  类组件有生命周期钩子，函数组件没有
4.  类组件可以定义并维护自己的 state，属于有状态组件，函数组件是无状态组件
5.  类组件需要继承 class，函数组件不需要
6.  类组件使用的是面向对象的方法，封装：组件属性和方法都封装在组件内部 继承:通过 extends React.Component 继承;函数组件使用的是函数式编程思想

_**why React hooks**_

优点：

1.  告别难以理解的 class 组件
2.  解决业务逻辑难以拆分的问题
3.  使状态逻辑复用变的简单可行
4.  函数组件从设计理念来看，更适合 react

局限性：

1.  hooks 还不能完整的为函数组件提供类组件的能力
2.  函数组件给了我们一定程度的自由，却也对开发者的水平提出了更高的要求
3.  Hooks 在使用层面有着严格的规则约束

_**常用 hooks**_

**useState**

[juejin.cn/post/711893…](https://juejin.cn/post/7118937685653192735#heading-4 "https://juejin.cn/post/7118937685653192735#heading-4")

## 十一、[**SetState 是同步还是异步的**](https://juejin.cn/post/7108362046369955847 "https://juejin.cn/post/7108362046369955847")

setState 是一个异步方法，但是在 setTimeout/setInterval 等定时器里逃脱了 React 对它的掌控，变成了同步方法

实现机制类似于 vue 的$nextTick 和浏览器的事件循环机制，每个 setState 都会被 react 加入到任务队列，多次对同一个 state 使用 setState 只会返回最后一次的结果，因为它不是立刻就更新，而是先放在队列中，等时机成熟在执行批量更新。React18 以后，使用了 createRoot api 后，所有 setState 都是异步批量执行的

## 十二、fiber 架构

**什么是 fiber，fiber 解决了什么问题**

在 React16 以前，React 更新是通过**树的深度优先遍历**完成的，遍历是不能中断的，当树的层级深就会产生栈的层级过深，页面渲染速度变慢的问题，为了解决这个问题引入了 fiber，React fiber 就是虚拟 DOM，它是一个链表结构，返回了 return、children、siblings，分别代表父 fiber，子 fiber 和兄弟 fiber，随时可中断

**Fiber 是纤程，比线程更精细，表示对渲染线程实现更精细的控制**

**应用目的**  
实现增量渲染，增量渲染指的是把一个渲染任务分解为多个渲染任务，而后将其分散到多个帧里。增量渲染是为了实现任务的可中断、可恢复，并按优先级处理任务，从而达到更顺滑的用户体验

**Fiber 的可中断、可恢复怎么实现的**

**_fiber_**是协程，是比线程更小的单元，可以被人为中断和恢复，当 react 更新时间超过 1 帧时，会产生视觉卡顿的效果，因此我们可以通过 fiber 把浏览器渲染过程分段执行，每执行一会就让出主线程控制权，执行优先级更高的任务

fiber 是一个链表结构，它有三个指针，分别记录了当前节点的下一个兄弟节点，子节点，父节点。当遍历中断时，它是可以恢复的，只需要保留当前节点的索引，就能根据索引找到对应的节点

**Fiber 更新机制**

**初始化**

1.  创建 fiberRoot（React 根元素）和 rootFiber(通过 ReactDOM.render 或者 ReactDOM.createRoot 创建出来的)
2.  进入 beginWork

**workInProgress**:正在内存中构建的 fiber 树叫 workInProgress fiber，在第一次更新时，所有的更新都发生在 workInProgress 树，在第一次更新后，workInProgress 树上的状态是最新状态，它会替换 current 树

**current**:正在视图层渲染的树叫 current fiber 树

```
currentFiber.alternate = workInProgressFiber
workInProgressFiber.alternate = currentFiber

```

3.  深度调和子节点，渲染视图

在新建的 alternate 树上，完成整个子节点的遍历，包括 fiber 的创建，最后会以 workInProgress 树最为最新的渲染树，fiberRoot 的 current 指针指向 workInProgress 使其变成 current fiber，完成初始化流程

**更新**

1.  重新创建 workInProgress 树，复用当前 current 树上的 alternate，作为新的 workInProgress

渲染完成后，workInProgress 树又变成 current 树

**双缓冲模式**

话剧演出中，演员需要切换不同的场景，以一个一小时话剧来说，在舞台中切换场景，时间来不及。一般是准备两个舞台，切换场景从左边舞台到右边舞台演出

在计算机图形领域，通过让图形硬件交替读取两套缓冲数据，可以实现画面的无缝切换，减少视觉的抖动甚至卡顿。

react 的 current 树和 workInProgress 树使用双缓冲模式，可以减少 fiber 节点的开销，减少性能损耗

**React 渲染流程**

如图，React 用 JSX 描述页面，JSX 经过 babel 编译为 render function，执行后产生 VDOM，VDOM 不是直接渲染的，会先转换为 fiber，再进行渲染。vdom 转换为 fiber 的过程叫 reconcile，转换过程会创建 DOM，全部转换完成后会一次性 commit 到 DOM，这个过程不是一次性的，而是可打断的，这就是 fiber 架构的渲染流程

![](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/d05402136ac44f87971d9f0b89466911~tplv-k3u1fbpfcp-zoom-in-crop-mark:3024:0:0:0.image)

vdom（React Element 对象）中只记录了子节点，没有记录兄弟节点，因此渲染不可打断

fiber（fiberNode 对象）是一个链表，它记录了父节点、兄弟节点、子节点，因此是可以打断的
