# FlexBox 布局

### 一、FlexBox布局请参考如下教程：

- [Flex 布局教程：语法篇](http://www.ruanyifeng.com/blog/2015/07/flex-grammar.html)
- [Flex 布局教程：实例篇](http://www.ruanyifeng.com/blog/2015/07/flex-examples.html)

### 二、**注**:

##### 1. 因为 ReactNative 没有完整实现 css 布局, 所以有些属性是不支持的, 具体可以参考：

- [ReactNative 样式](http://reactnative.cn/docs/0.26/style.html#content)

##### 2. ReactNative 样式 与 Css 写法差异（除不兼容属性）：

css写法：

```
.box {
  display: flex;
  justify-content: center;
  align-items: center;
}
```

ReactNative 写法：

```
var styles = StyleSheet.create({
  base: {
    width: 38,
    height: 38,
  },
  background: {
    backgroundColor: '#222222',
  },
  active: {
    borderWidth: 2,
    borderColor: '#00ff00',
  },
});
```

可以看到 RN 的写法出了需要使用 `StyleSheet.create` 创建外, 还在每个选择器右边多了一个 `:` 符号, 并且所有的属性都需要使用 **驼峰命名法** 进行书写。