# 语法

## 一、let和const命令

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