# 安装依赖
```
yarn add react-router-dom
```

## react-router基本使用

## react-router最主要的API是给我们提供的一些组件

- BrowserRouter或HashRouter

- - Router中包含了对路径改变的监听，并且会将相应的路径传递给子组件；
  - BrowserRouter使用history模式；
  - HashRouter使用hash模式；

- Link和NavLink：

- - 通常路径的跳转是使用Link组件，最终会被渲染成a元素；
  - NavLink是在Link基础之上增加了一些样式属性（后续学习）；
  - to属性：Link中最重要的属性，用于设置跳转到的路径；

- Route：

- - Route用于路径的匹配；

  - path属性：用于设置匹配到的路径；

  - component属性：设置匹配到路径后，渲染的组件；

  - exact：精准匹配，只有精准匹配到完全一致的路径，才会渲染对应的组件；
## react-router实际使用
```jsx
import React, { PureComponent } from 'react';
import { BrowserRouter, Route, Link } from 'react-router-dom';

import Home from './pages/home';
import About from './pages/about';
import Profile from './pages/profile';

export default class App extends PureComponent {
  render() {
    return (
      {/*使用路由需要包裹BrowserRouter或HashRouter*/}
      <BrowserRouter>
        {/* Link 用于跳转*/}
        <Link to="/">首页</Link>
        <Link to="/about">关于</Link>
        <Link to="/profile">我的</Link>
        
        {/* Route 用于匹配路由*/}
        <Route exact path="/" component={Home} />
        <Route path="/about" component={About} />
        <Route path="/profile" component={Profile} />
      </BrowserRouter>
    )
  }
}
```

## NavLink的使用