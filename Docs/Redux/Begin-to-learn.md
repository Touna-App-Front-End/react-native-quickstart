# 开始学习

因为我们最终是开发 ReactNative 应用, 所以这里打算一起做一个简单的 "工作流" 应用来一起学习 Redux. 里面涉及到的技术有:

1. immutable.js

Facebook 出的一款一旦被创造后，就不可以被改变的数据的js框架. 虽然你可以用 ES2015 的新特性 [Object.assign()](http://es6.ruanyifeng.com/#docs/object#Object-assign), 但是他还是属于浅拷贝, 请看如下代码运行结果

[![alt text](http://p.simman.cc/2016-06-15_1465933180969391984.png "title")](https://jsbin.com/tefusuc/1/edit?js,console)

所以你需要使用 immutable.js

- react
- react-native
- react-redux
- redux
- redux-logger
- redux-thunk: 异步Action
