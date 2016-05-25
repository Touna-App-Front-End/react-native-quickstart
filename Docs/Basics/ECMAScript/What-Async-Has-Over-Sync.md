# 同步与异步

## 一、JavaScript是单线程

众所周知, Javascript 是单线程运行的, 是因为当时设计 Javascript 的初衷为用户交互、操作 DOM, 这决定了它只能是单线程，否则会带来很复杂的同步问题。比如，假定JavaScript同时有两个线程，一个线程在某个DOM节点上添加内容，另一个线程删除了这个节点，这时浏览器应该以哪个线程为准？

**每个window一个JS线程??**


## 二、浏览器不是单线程

虽然JS运行在浏览器中，是单线程的，每个window一个JS线程，但浏览器不是单线程的，例如Webkit或是Gecko引擎，都可能有如下线程：

- javascript引擎线程
- 界面渲染线程
- 浏览器事件触发线程
- Http请求线程
- 
很多童鞋搞不清，如果js是单线程的，那么谁去轮询大的Event loop事件队列？答案是浏览器会有单独的线程去处理这个队列。

## 三、JavaScript 运行机制详解

![2016-05-25_1464168842851303527.png](http://p.simman.cc/2016-05-25_1464168842851303527.png)


## 四、定时器
```
console.log(1);
setTimeout(function(){console.log(2);},1000);
console.log(3);
```

```
setTimeout(function(){console.log(1);}, 0);
console.log(2);
```

## 五、异步模式的四种方法

### 5.1 回调函数

```
function f1(callback){
  setTimeout(function () {
    console.log('my name is f1...');
    callback();
  }, 1000);
}

function f2() {
  console.log('my name is f2...');
}

f1(f2);

console.log('========= end =========');

// log
========= end =========
my name is f1...
my name is f2...
```

[source code](https://jsfiddle.net/liwei0990/d3ngc42c/)

### 5.2 事件监听



### 5.3 发布/订阅 （观察者)

### 5.4 Promises对象



## 六、Web Worker

Web Worker 是HTML5标准的一部分，这一规范定义了一套 API，它允许一段JavaScript程序运行在主线程之外的另外一个线程中。Web Worker 规范中定义了两类工作线程，分别是专用线程Dedicated Worker和共享线程 Shared Worker，其中，Dedicated Worker只能为一个页面所使用，而Shared Worker则可以被多个页面所共享。

为了利用多核CPU的计算能力，HTML5提出的Web Worker标准，允许JavaScript脚本创建多个线程，但是子线程完全受主线程控制，且不得操作DOM。所以，这个新标准并没有改变JavaScript单线程的本质。

更多内容请参考:

- [【转向Javascript系列】深入理解Web Worker](http://www.alloyteam.com/2015/11/deep-in-web-worker/)
-  [js多线程运行之web worker](http://www.yi-jy.com/2014/09/19/js%E5%A4%9A%E7%BA%BF%E7%A8%8B%E8%BF%90%E8%A1%8C%E4%B9%8Bweb-worker/)
-  [Web Workers 的基本信息](http://www.html5rocks.com/zh/tutorials/workers/basics/)


## 异步编程

- [Javascript异步编程的4种方法](http://www.ruanyifeng.com/blog/2012/12/asynchronous%EF%BC%BFjavascript.html)
- [JavaScript异步编程原理](http://www.cnblogs.com/hustskyking/p/javascript-asynchronous-programming.html)
- [JavaScript 运行机制详解：再谈Event Loop](http://www.ruanyifeng.com/blog/2014/10/event-loop.html)
- [Javascript是单线程的深入分析](http://www.cnblogs.com/Mainz/p/3552717.html)
- [异步操作和Async函数](http://es6.ruanyifeng.com/#docs/async)
- 
