# 环境安装

1、安装Xcode最新版 (里面包含了常用的开发环境,如git)

2、安装 Iterm2、Oh My Zsh (可选安装)

1. [Iterm2](https://www.iterm2.com) 比原生的 Terminal 增加了很多的特性.
2. [Oh My Zsh](http://ohmyz.sh/) 

参考自: [菜鸟级 Mac 配置（二）](http://geekplux.com/2014/03/03/mac_configuration_2.html)

3、安装 Homebrew (Mac os x上的包管理,如Ubuntu的 apt-get)

```
ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

4、安装 nvm (nodejs 的版本管理)

```
git clone https://github.com/cnpm/nvm.git ~/.nvm && cd ~/.nvm && git checkout `git describe --abbrev=0 --tags`

. ~/.nvm/nvm.sh
```

然后打开 ~/.bashrc 、 ~/.profile , or  ~/.zshrc这三个文件，在其中添加：

**注: ** 上面的文件可能会没有,请自行创建, 如果安装了 oh my zsh , 会自动生成 .zshrc 文件

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
9、安装 rnpm (React Native Package Manager)

```
npm install -g rnpm
```

10、创建项目

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

11、设置依赖并运行

```
npm install
rnpm link
react-native run-ios
npm start
```

