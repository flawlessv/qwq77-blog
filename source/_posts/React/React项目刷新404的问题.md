---
title: React项目刷新404的问题
tags:
  - React
---
在`React`项目中，刷新页面时出现`404`错误可能是因为当你使用`react-router-dom`进行路由跳转时，应用程序默认使用了`HTML5`的`history`模式。在这种模式下，刷新页面将尝试访问服务器端的相同`URL`地址，但通常会返回`404`，因为此URL地址并不存在于服务器上。

要解决这个问题，你可以考虑使用服务器端渲染或基于`Node.js`的服务器框架来处理这些`URL`地址。如果你不想使用服务器端渲染，可以尝试使用`HashRouter`方式，它将使用 `hash` 值而不是 `history API` 来管理路由状态。

例如，你可以按照以下步骤进行更改：

在你的React项目中安装 `react-router-dom` 和 `react-router-hash-link` 包:

`npm install react-router-dom react-router-hash-link --save`
在你的应用程序中引入 `HashRouter` 而不是 `BrowserRouter`：

```javascript
import { HashRouter, Switch, Route } from 'react-router-dom';

function App() {
  return (
    <HashRouter>
      <Switch>
        <Route exact path="/" component={Home} />
        <Route path="/about" component={About} />
        ...
      </Switch>
    </HashRouter>
  );
}```
如果你需要使用导航链接，请使用 HashLink 而不是普通链接：

```javascript
import { HashLink as Link } from 'react-router-hash-link';

function Navbar() {
  return (
    <nav>
      <ul>
        <li>
          <Link smooth to="/#section1">
            Section 1
          </Link>
        </li>
        ...
      </ul>
    </nav>
  );
}```
这样，当你在浏览器中刷新页面时，它将使用 hash 值来访问路由，而不是尝试使用 history API 来访问URL地址并更新应用程序状态。