# 环境安装

1、安装Xcode最新版 (里面包含了常用的开发环境,如git)

2、安装 Iterm2、Oh My Zsh (可选安装)

   2.1、[Iterm2](https://www.iterm2.com) 比原生的 Terminal 增加了很多的特性, 如: 

  1.  分窗口操作：shift+command+d（横向）command+d（竖向）
  2.  查找和粘贴：command+f，呼出查找功能，tab 键选中找到的文本，option+enter 粘贴
  3.  自动完成：command+ 根据上下文呼出自动完成窗口，上下键选择
  4.  粘贴历史：shift+command+h
  5.  回放功能：option+command+b
  6.  全屏：command+enter
  7.  光标去哪了？ command+/
  8.  Expose Tabs：option+command+e

  更多内容请参考: [iTerm2新手应知特色功能](http://www.yangzhiping.com/tech/iterm2.html)

2、[Oh My Zsh](http://ohmyz.sh/)

3、安装 Homebrew (Mac os x上的包管理,如Ubuntu的 apt-get)

```
ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

4、安装 nvm (nodejs 的版本管理)

```
git clone https://github.com/cnpm/nvm.git ~/.nvm && cd ~/.nvm && git checkout `git describe --abbrev=0 --tags`

. ~/.nvm/nvm.sh
```

然后打开 ~/.bashrc ,  ~/.profile , or  ~/.zshrc这三个文件，在其中添加：

```
source ~/.nvm/nvm.sh
```

5、安装nodejs

```
nvm install node && nvm alias default node
```

6、安装 cnpm (node 的包管理为 npm，因为天朝原因,故推荐taobao的 cnpm)

```
npm install -g cnpm --registry=https://registry.npm.taobao.org
```

7、安装 `watchman`  (实时监测文件修改), `flow` (JavaScript 的静态类型检查器)

```
brew install watchman
brew install flow
```
8、安装 react-native-cli

```
cnpm install -g react-native-cli
```

9、创建项目

```
react-native init hello
```

加上 `--verbose` 显示安装详细信息

目录结构如下：

```
.
├── android
├── index.android.js
├── index.ios.js
├── ios
├── node_modules
├── npm-debug.log
└── package.json

2695 directories, 14329 files
```