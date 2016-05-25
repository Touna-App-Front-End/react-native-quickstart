# 环境安装

1、安装Xcode最新版 (里面包含了常用的开发环境,如git)

2、安装 Homebrew (Mac os x上的包管理,如Ubuntu的 apt-get)

```
ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

3、安装 nvm (nodejs 的版本管理)

```
git clone https://github.com/cnpm/nvm.git ~/.nvm && cd ~/.nvm && git checkout `git describe --abbrev=0 --tags`

. ~/.nvm/nvm.sh
```

然后打开 ~/.bashrc ,  ~/.profile , or  ~/.zshrc这三个文件，在其中添加：

```
source ~/.nvm/nvm.sh
```

4、安装nodejs

```
nvm install node && nvm alias default node
```

5、安装 cnpm (node 的包管理为 npm，因为天朝原因,故推荐taobao的 cnpm)

```
npm install -g cnpm --registry=https://registry.npm.taobao.org
```

6、安装 `watchman`  (实时监测文件修改), `flow` (JavaScript 的静态类型检查器)

```
brew install watchman
brew install flow
```
7、安装 react-native-cli

```
cnpm install -g react-native-cli
```

8、创建项目

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