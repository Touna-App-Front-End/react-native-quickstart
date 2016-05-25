# 同步与异步

## 一、JavaScript是单线程

众所周知, Javascript 是单线程运行的, 是因为当时设计 Javascript 的初衷为用户交互、操作 DOM, 这决定了它只能是单线程，否则会带来很复杂的同步问题。比如，假定JavaScript同时有两个线程，一个线程在某个DOM节点上添加内容，另一个线程删除了这个节点，这时浏览器应该以哪个线程为准？

## 二、


## HTML5 的新Api web worker

Web Worker 是HTML5标准的一部分，这一规范定义了一套 API，它允许一段JavaScript程序运行在主线程之外的另外一个线程中。Web Worker 规范中定义了两类工作线程，分别是专用线程Dedicated Worker和共享线程 Shared Worker，其中，Dedicated Worker只能为一个页面所使用，而Shared Worker则可以被多个页面所共享。

更多内容请参考:

- [【转向Javascript系列】深入理解Web Worker](http://www.alloyteam.com/2015/11/deep-in-web-worker/)
-  [js多线程运行之web worker](http://www.yi-jy.com/2014/09/19/js%E5%A4%9A%E7%BA%BF%E7%A8%8B%E8%BF%90%E8%A1%8C%E4%B9%8Bweb-worker/)
-  [Web Workers 的基本信息](http://www.html5rocks.com/zh/tutorials/workers/basics/)