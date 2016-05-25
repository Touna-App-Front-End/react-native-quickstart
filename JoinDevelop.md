# 加入项目开发


## 一、如何加入项目

1. 首先去 [coding.net](https://coding.net/register?key=017c2cd0-97d8-40e5-9a29-38071c245bd1) 注册一个账号, 注册完后需要把 邮箱或者用户名 发送给 @simman
2. 待 @simman 通过申请以后, 请自行进入项目, 拉去最新的代码. 
3. coding.net 与 git、git gui 的使用与推荐情参考：[Git使用教程](https://simman.gitbooks.io/rnrstudy/content/Docs/Basics/GIT/)

## 二、每日必做

1. 每晚 5.30 小例会同步进度, 并发送给 @simman 进行汇总. (5分钟左右)

## 三、代码规范

目前所有自行编写的模块必须使用 ES6、ES7 语法进行替换, 最后会使用工具进行检查, 请参考一下链接:

- [React Native 代码规范](https://github.com/sunnylqm/react-native-coding-style) (airbnb&广发证券前端)
- [React/React Native 的ES5 ES6写法对照表](http://bbs.reactnative.cn/topic/15/react-react-native-%E7%9A%84es5-es6%E5%86%99%E6%B3%95%E5%AF%B9%E7%85%A7%E8%A1%A8)

## 四、版本控制

请务必使用 develp 分支, 或者自行建立分支, 最后合并到 develp 分支上。

	```
	master
	* develop
	```

## 五、Code Templates

1. 新创建的文件, 模版为:

	```
	'use strict';
	/**
	 * ${JS File Name}.js
	 *
	 * @des the file dees
	 * @author ${USER} (liwei0990#gmail.com)
	 * Created at ${DATE}.
	 * Copyright 2011-2016 Touna.cn, Inc.
	 */
	```

2. 修改文件的的注释为: 

	```
	// 16.5.14 @simman fix bug
	```

## 六、目录规范

1、所有文件的命名需要使用 **模块名 + 类型 .js**

2、所有的 Reducer、InitialState、Action 需要放置在 `/reducers/模块名称`.

3、component 下面的文件需要命名为 **组件名称 + .component.js**

4、尽量抽离 styles 为单独的文件, 命名规则为 **组件名称 + .styles.js**, 尽量不要直接写在组件上面。

```
.
├── README.md
├── app
│   ├── actions
│   ├── apis
│   │   ├── net
│   │   │   ├── HTTPClient.js
│   │   │   ├── Params.js
│   │   │   ├── TNWFetch.js
│   │   │   └── middleware
│   │   │       ├── RequestMiddleware.js
│   │   │       └── ResponseMiddleware.js
│   │   └── service
│   │       ├── authServer.js
│   │       ├── financeServer.js
│   │       └── tenderServer.js
│   ├── component
│   │   ├── CustomTabbar.js
│   │   ├── FormButton.js
│   │   ├── GestureLock
│   │   │   ├── circle.js
│   │   │   ├── helper.js
│   │   │   ├── index.js
│   │   │   └── line.js
│   │   └── user
│   │       ├── AgreeView.js
│   │       ├── RegistFirstView.js
│   │       └── RegisterTwoView.js
│   ├── config
│   │   └── config.js
│   ├── constants
│   │   ├── ActionTypes.js
│   │   ├── Constants.js
│   │   └── URLs.js
│   ├── containers
│   │   ├── Account.js
│   │   ├── Finance.js
│   │   ├── GestureLock.js
│   │   ├── Interact.js
│   │   ├── Invest.js
│   │   ├── Launch.js
│   │   ├── SelectTender.js
│   │   ├── Splash.js
│   │   └── user
│   │       ├── GesturePwd.js
│   │       ├── LoginIndex.js
│   │       ├── LoginTwo.js
│   │       ├── RegisterIndex.js
│   │       └── RegisterTwo.js
│   ├── index.js
│   ├── reducers
│   │   ├── finance
│   │   │   ├── financeAction.js
│   │   │   ├── financeReducer.js
│   │   │   └── financeState.js
│   │   ├── index.js
│   │   └── user
│   │       └── auth
│   │           ├── authAction.js
│   │           ├── authInitialState.js
│   │           └── authReducer.js
│   ├── static
│   │   ├── font
│   │   ├── images
│   │   │   ├── Android
│   │   │   │   └── interactio_bg.png
│   │   │   ├── common
│   │   │   │   ├── Input
│   │   │   │   │   ├── register_visiblepassword_icon@2x.png
│   │   │   │   │   └── register_visiblepassword_icon@3x.png
│   │   │   │   ├── loading
│   │   │   │   │   └── loading_center.gif
│   │   │   │   └── register
│   │   │   │       └── register_index.png
│   │   │   └── iOS
│   │   │       └── Tab
│   │   │           ├── zichan_icon_Click.ios@2x.png
│   │   │           └── zichan_icon_Click.ios@3x.png
│   │   ├── page
│   │   └── style
│   ├── store
│   │   ├── configureStore.js
│   │   └── globalStorage.js
│   └── util
│       └── RSAUtil.js
├── index.android.js
├── index.ios.js
├── package.json
├── tsconfig.json
└── update.json

41 directories, 104 files
 
```

在component和page目录中，可能还有一些内聚度较高的模块再建目录

```
src/component
├── HomeView.component.js
├── HomeView.style.js
└── MovieView
    ├── MovieList.component.js  		
    ├── MovieList.style.js       	
    ├── MovieCell.component.js 			
    ├── MovieCell.style.js				
    ├── MovieView.component.js			
    └── MovieView.style.js				
```


## 推荐资料
- [React-Native指南](https://github.com/ele828/react-native-guide) (资料很全)