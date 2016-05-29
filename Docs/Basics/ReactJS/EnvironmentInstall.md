# 环境搭建

在 React.js 的课程中我们将要做一个小App, 大概的功能如下:

- 用户登陆
- 用户注册
- 用户登出
- 发布推特（需要登录态)
- 查看推特列表


# 服务器程序

可以看到上面的功能完成需要服务器的支持, 所以我们先来搞定服务器, 这里为了演示方便, 也为了大家可以看得懂, 这里使用了 node.js 编写了一个简单的服务器应用.

当然为了方便你可以直接在 Github 上面下载我已经编写好的程序。

[https://github.com/Touna-App-Front-End/simple-user-center-server](https://github.com/Touna-App-Front-End/simple-user-center-server)

# 本地环境

ok, 为了能更方便简洁的安装 React.js 环境, 我们使用 jspm 工具, jspm 是一个浏览器端包管理器, 更多介绍轻访问官网 [jspm.io](http://jspm.io/).

1、首先我们现在本地新建一个目录, 在教程里取名为 `reactjs-tutorial-app` , 当然你没有必要和我的名字一样.

2、安装 jspm 工具

```
npm install -g jspm
```

3、安装 React.js

```
jspm install react
```

4、安装 React DOM

```
jspm install react-dom
```

5、本教程使用 `semantic-ui` 这个css库来完成样式.

```
jspm install semantic-ui
jspm install css
```

6、创建应用的程序目录, 教程里取名为 `app`, 并在目录下创建一个 `index.js` 用来编写我们的应用.

7、在根目录创建 `index.html` 文件. 并且在里面输入如下内容

```
<!DOCTYPE html>
<html>
<head>
    <meta charset="utf-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <title>reactjs-tutorial-app</title>
</head>
<body>
    <div id="ui container">
        <div id="app"></div>
    </div>

    <script src="jspm_packages/system.js"></script>
    <script src="config.js"></script>
    <script>
        System.import('app/index');
    </script>
</body>
</html>
```
8、然后我们使用 `browser-sync` 来监控文件变化

```
browser-sync start --server --files "*.html, app/**/*.js"
```

ok, 到此我们最基本的 React.js 开发环境已经完成, 下面是环境的安装的视频演示, 如果你已经配置好, 请直接进入下一课程.

