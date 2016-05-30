# 用户注册
现在我们正式开始进入编写 React.js 了, 前面说过这个 App 的功能, 第一个就是 **用户注册**, 我们先来看一下注册页面的设计图.

![2016-05-30_1464579294101550945.png](http://p.simman.cc/2016-05-30_1464579294101550945.png!800)
页面共分为3个部分

- 头部, 显示当前页面的标题
- 主体, 显示注册表单
- 尾部, 显示提示性文字

## 开始编码

首先我们打开根目录下的 index.js 文件, 在里面写入下面代码:

```
'use strict';

import 'semantic-ui/semantic.min.css!';
import React from 'react';
import ReactDOM from 'react-dom';

ReactDOM.render(
  <Button />,
  document.getElementById('app')
);
```
第一步是引入 semanticui 的css文件, 这个文件之前我们使用了 jspm 安装过了, 结尾的 ! 代表使用 css 插件进行处理。

第二步是引入 React 和 ReactDOM

第三步是使用 `ReactDOM.render()` 方法进行 实例化根组件，启动框架，把标记注入到第二个参数指定的原生的 DOM 元素中。ReactDOM 模块提供了一些 DOM 相关的方法，而 React 模块包含了 React 团队分享的不同平台上的核心工具（例如， React Native ）。

