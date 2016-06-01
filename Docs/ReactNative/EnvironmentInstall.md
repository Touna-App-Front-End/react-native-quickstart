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

6、替换 npm 仓库为淘宝国内源

```
npm config set registry https://registry.npm.taobao.org --global
npm config set disturl https://npm.taobao.org/dist --global
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

> 另，执行init时切记不要在前面加上sudo（否则新项目的目录所有者会变为root而不是当前用户，导致一系列权限问题，请使用chown修复）。

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

### 参考链接

- [React Native的常见问题](http://bbs.reactnative.cn/topic/130/%E6%96%B0%E6%89%8B%E6%8F%90%E9%97%AE%E5%89%8D%E5%85%88%E6%9D%A5%E8%BF%99%E9%87%8C%E7%9C%8B%E7%9C%8B-react-native%E7%9A%84%E5%B8%B8%E8%A7%81%E9%97%AE%E9%A2%98)
- [React Native疑难点,问题深坑最强总结帖](http://www.lcode.org/react-native%E7%96%91%E9%9A%BE%E7%82%B9%E9%97%AE%E9%A2%98%E6%B7%B1%E5%9D%91%E6%9C%80%E5%BC%BA%E6%80%BB%E7%BB%93%E5%B8%96%E4%B8%8D%E6%96%AD%E6%9B%B4%E6%96%B0%E4%B8%AD/)
