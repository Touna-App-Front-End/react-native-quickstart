# Redux 简介

## 一、什么是 Redux？

Redux 是 JavaScript 状态容器，提供可预测化的状态管理。

## 二、WTF？请说人话.

👌, Redux 就是 MVC 模式中的 MC, 而 React 就是其中的 V.

## 三、Redux 核心概念

### 3.1 单一数据源

整个应用的 state 被储存在一棵 object tree 中，并且这个 object tree 只存在于唯一一个 store 中。

### 3.2 State 是只读的

惟一改变 state 的方法就是触发 action，action 是一个用于描述已发生事件的普通对象。

### 3.3 使用纯函数来执行修改

为了描述 action 如何改变 state tree ，你需要编写 reducers。

## 四、总结

在一个应用中有且只有一个 Store 来存储 state, 并且数据流完全根据如下方式进行传递:

![2016-06-15_1465928976336872926.png](http://p.simman.cc/2016-06-15_1465928976336872926.png)