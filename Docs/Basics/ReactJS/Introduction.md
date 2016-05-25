# React.js 简介

## 一、什么是 React.js

React.js 是一个用于构建用户界面的**可复用**、**可聚合**的JAVASCRIPT库.

当然你还要要明白如下几点:

- 它不是 MVC 框架, 它只提供了 MVC 框架中的 **V**.
- 虚拟DOM, React为了更高超的性能而使用虚拟DOM作为其不同的实现。
- 单向数据流, React并不像 AngularJS 一样数据双向绑定, 它实现了单向响应的数据流，从而减少了重复代码. 当然你也可以用一些其他方法, 使它支持双向数据流.

## 二、哪些公司使用 React.js

推荐与介绍一款框架首先需要指出有哪些真实项目使用了它, 这样你才会放心, 因为它是经过考验的.

下面简单列出一些: (当然, 并不是指的全站, 有的是部分模块)

- Facebook 
- Instagram
- Twitter
- Apple
- 天猫
- 淘宝
- 豆瓣
- 知乎
- 卖座
- 六间房

更多请看：

- [Sites Using React](https://github.com/facebook/react/wiki/Sites-Using-React)
- [哪里有比较成熟的 React.js 项目案例？](https://www.zhihu.com/question/30849772)

## 三、为什么使用 React.js ?

首先要再说明一下 React isn't an MVC framework. 所以不要用它直接和 AngularJS 去比较, 因为 AngularJS 是一个 MVC 框架, 并且自带的数据绑定、渲染、事件管理、路由、ajax……等等一系列工具。

### 3.1 JS 逻辑与HTML紧密相连, 毫无违和感.

AngularJS 实现:

```
app.directive('messageBox', function() {
    return {
	    restrict: 'E',
	    template: '<div> \
	                <h1 ng-click="alert()">Hello world</h1> \
	                <p>My Name Is Hellooooooooo</p> \
	               </div>',
	    link: function($scope) {
	            $scope.alert = function() {
	                alert('😄');
	            }
	          }
	    }
});
```

React.js 实现:

```
var MessageBox = React.createClass({
    alert: function() {
        alert('😄');
    },

    render: function() {
        return (
            <div>
                <h1 onClick={this.alert()}>Hello world!</h1>
                <p>My Name Is Hellooooooooo</p>
            </div>
        )
    }
});
```

上面看到了一些区别, 最明显的就是为啥 JS 能和 HTML 写到一起, 这里就要提一下 JSX 的概念了。

**JSX** 是一个看起来很像 XML 的 JavaScript 语法扩展。React 可以用来做简单的 JSX 句法转换。

当然如果你喜欢使用 html 语法的话, 在 React.js 里面也是可行的. 你完全可以选择是否使用 JSX，并不是 React 必须的。你可以通过 React.createElement 来创建一个树。第一个参数是标签，第二个参数是一个属性对象，第三个是子节点。

示例代码:

```
var child = React.createElement('li', null, 'Text Content');
var root = React.createElement('ul', { className: 'my-list' }, child);
React.render(root, document.body);
```

### 3.2 单向数据流

1、

