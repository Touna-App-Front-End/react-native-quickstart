# 一、Redux 简介

## 1.1 什么是 Redux？

Redux 是 JavaScript 状态容器，提供可预测化的状态管理。


## 1.2 WTF？请说人话.

👌, Redux 就是 MVC 模式中的 MC, 而 React 就是其中的 V.

## 1.3 Redux 核心概念

#### 1.3.1 单一数据源

整个应用的 state 被储存在一棵 object tree 中，并且这个 object tree 只存在于唯一一个 store 中。

#### 1.3.2 State 是只读的

惟一改变 state 的方法就是触发 action，action 是一个用于描述已发生事件的普通对象。

#### 1.3.2 使用纯函数来执行修改

为了描述 action 如何改变 state tree ，你需要编写 reducers。


## 1.4 总结

在一个应用中有且只有一个 Store 来存储 state, 并且数据流完全根据如下方式进行传递: