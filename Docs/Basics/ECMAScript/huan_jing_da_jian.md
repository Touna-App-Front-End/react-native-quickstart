# 环境搭建

1. 创建 **ECMAScript** 目录 

2. 进入 **ECMAScript** 目录, 运行 `npm init` 命令.

3. 因为项目中要使用 es6 , 但是很多浏览器目前还不完全支持, 详情 [点击这里](https://kangax.github.io/compat-table/es6/), 所以我们需要安装 babel , babel 是可以转换 es6 代码到 es5 的一个 node.js 的包工具。

	```
	npm install --save-dev babel-cli babel-preset-es2015
	```

4. 为了可以在我们编写完 js 代码后, 浏览器可以自动刷新, 我们需要安装如下的包：

	```
	npm install --save-dev browser-sync
	```

5. 这里我们为了可以让文件在修改后, 先进行 es6 转换, 然后再自动刷新浏览器, 我们使用 `gulp` 任务管理器来完成这些操作。

	```
	npm install --save-dev gulp gulp-babel gulp-notify gulp-util
	```
	
	```
	npm install --save-dev babelify vinyl-buffer vinyl-source-stream watchify
	```

6. 创建 **babel** 的配置文件 .babelrc, 然后填写如下内容:

	```
	{
	  "presets": [
	      "es2015"
	  ],
	  "plugins": []
	}
	```

7. 创建 **gulp** 配置文件, gulpfile.babel.js, 内容如下:

	```
	var browserSync = require("browser-sync").create();
	const gulp = require('gulp');
	const babelify = require('babelify');
	const browserify = require('browserify');
	const watchify = require('watchify');
	var gutil = require("gulp-util");
	var notify = require('gulp-notify');
	var source = require("vinyl-source-stream");
	var buffer = require('vinyl-buffer');
	
	gulp.task("watch", function() {
	  var b = browserify({
	    entries: ['scripts/index.js']
	  }).transform(babelify);
	
	  function bundle() {
	    b.bundle()
	      .on("log", gutil.log)
	      .on("error", notify.onError())
	      .pipe(source('main.js'))
	      .pipe(buffer())
	      .pipe(gulp.dest('dist'))
	      .pipe(browserSync.reload({
	        stream: true
	      }));
	  }
	
	  watchify(b, {
	    delay: 60
	  }).on("update", bundle);
	  bundle();
	});
	
	gulp.task("serve", function() {
	  browserSync.init({
	    server: {
	      baseDir: "./"
	    }
	  });
	});
	
	gulp.task("default", ["watch", "serve"]);
	```

8. 创建项目目录, 结构如下

	```
	ECMAScript|⇒ tree -I 'node_modules' -L 2 -a
	.
	├── .babelrc
	├── gulpfile.babel.js
	├── index.html
	├── package.json
	├── scripts
	│   └── index.js
	└── styles
	    └── style.css
	
	2 directories, 6 files
	```

9. 运行命令 `gulp` .