---
title: useEffect和useLayoutEffect的区别
tags:
  - React
  - 
---
1. useEffect 是异步非阻塞，useLayoutEffect 是同步阻塞。
2. useEffect 是在浏览器绘制之后执行，useLayoutEffect 是在 DOM 变更之后，浏览器绘制前执行
3. useLayoutEffect和componentDidMount是等价的，会同步调用，阻塞渲染
4. 会影响到渲染的操作尽量放到 useLayoutEffect中去，避免出现闪烁问题
5. 优先使用 useEffect，因为它是异步执行的，不会阻塞渲染
6. useLayoutEffect 会阻塞 DOM 的渲染，避免过度使用
