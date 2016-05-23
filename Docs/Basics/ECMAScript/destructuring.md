# 变量的结构赋值

### 1、数组的解构赋值

#### 1.1 基本用法

```
es5:

var a = 1,
	b = 2,
	c = 3;

es6:

var [a, b, c] = [1, 2, 3];
```

#### 1.2 默认值

```
var [a, b, c = 1] = [1, 2];

a = 1
b = 2
c = 1
```

**注意**: ES6内部使用严格相等运算符（===），判断一个位置是否有值。所以，如果一个数组成员不严格等于undefined，默认值是不会生效的。

### 2、对象的解构赋值

对象的解构赋值中, 变量必须与属性同名, 才能取到正确的值。

```
var { foo, bar } = { foo: "aaa", bar: "bbb" };
foo // "aaa"
bar // "bbb"
```

如果变量名称不一致, 则可以使用如下方式:

```
var { foo: xxx, bar: ooo } = { foo: "aaa", bar: "bbb" };

xxx: "aaa"
ooo: "bbb"
```

### 3、字符串的解构赋值

```
const [a, b, c, d, e] = 'hello';
a // "h"
b // "e"
c // "l"
d // "l"
e // "o"
```

### 4、数值和布尔值的解构赋值

```
let {toString: s} = 123;
s === Number.prototype.toString // true

let {toString: s} = true;
s === Boolean.prototype.toString // true
```

### 5、函数参数的解构赋值

```
function add([x, y]){
  return x + y;
}

add([1, 2]); // 3
```

### 6、用途

1. 交换变量的值

	```
	[x, y] = [y, x];
	```
2. 从函数返回多个值

	```
	// 返回一个数组
	function example() {
	  return [1, 2, 3];
	}
	var [a, b, c] = example();
	
	// 返回一个对象
	
	function example() {
	  return {
	    foo: 1,
	    bar: 2
	  };
	}
	var { foo, bar } = example();
	```
3. 输入模块的指定方法

	```
	import { Actions } from 'react-native-router-flux';
	```