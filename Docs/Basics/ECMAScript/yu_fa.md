# let和const命令

可以下载初始化的工程进行练习: 

```
https://github.com/Touna-App-Front-End/EMACScriptDemo
```
如果你打算自己创建工程可以参考：[环境搭建](./huan_jing_da_jian.md)


### 1. let 命令

#### 1.1 let 作用域

> ES6新增了let命令，用来声明变量。它的用法类似于var，但是所声明的变量，只在let命令所在的代码块内有效。 

```
{
  let apple = 🍎;
  var banana = 🍌;
}

apple // ReferenceError: a is not defined.
banana // 1
```

for 循环例子

```
for (let i = 0; i < 10; i++) {}
console.log(i); // i is not defined


for (var i = 0; i < 10; i++) {}
console.log(i); // 10
```

#### 1.2 变量提升

```
console.log(foo); // 输出undefined
console.log(bar); // 报错ReferenceError

var foo = 2;
let bar = 2;
```

#### 1.3 暂时性死区

> ES6明确规定，如果区块中存在let和const命令，这个区块对这些命令声明的变量，从一开始就形成了封闭作用域。凡是在声明之前就使用这些变量，就会报错。

```
var tmp = 123;

if (true) {
  tmp = 'abc'; // ReferenceError
  let tmp;
}
```

#### 1.4 不允许重复声明

```
// 报错
function funA() {
  let a = 10;
  var a = 1;
}

// 报错
function funB() {
  let a = 10;
  let a = 1;
}
```

#### 1.5 块级作用域

> ES5只有全局作用域和函数作用域，没有块级作用域，这带来很多不合理的场景。

```
var tmp = new Date();

function f() {
  console.log(tmp);
  if (false) {
    var tmp = "hello world";
  }
}

f(); // undefined
```

ES6的let实际上为JavaScript新增了块级作用域。

```
function f1() {
  let n = 5;
  if (true) {
    let n = 10;
  }
  console.log(n); // 5
}
```

另外，ES6也规定，函数本身的作用域，在其所在的块级作用域之内。

```
function f() { console.log('I am outside!'); }
(function () {
  if(false) {
    // 重复声明一次函数f
    function f() { console.log('I am inside!'); }
  }

  f();
}());
```

### 2. const 命令

> const 声明一个只读的常量。一旦声明，常量的值就不能改变。

```
const fruit = '🍎';
fruit = '🍊'; // TypeError: "fruit" is read-only
```

const 与 let 一样, 不存在:

- 只在声明所在的块级作用域内有效
- const命令声明的常量也是不提升
- 也与let一样不可重复声明

对于复合类型的变量，变量名不指向数据，而是指向数据所在的地址。

```
const fruits = {};
fruits.first = '🍎';
fruits.first; // 🍎 

fruits = {}; // TypeError: "fruits" is read-only
```

### 3. 全局对象的属性

- window : 浏览器环境
- global : Node.js 运行环境

ES6为了改变这一点，一方面规定，为了保持兼容性，var命令和function命令声明的全局变量，依旧是全局对象的属性；另一方面规定，let命令、const命令、class命令声明的全局变量，不属于全局对象的属性。也就是说，从ES6开始，全局变量将逐步与全局对象的属性脱钩。

