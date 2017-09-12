# ES6语法

## 数组的扩展

### 类数组的转换数组 Array.from()

类数组：本质特征是必有length属性

常用的类数组有：arguments，DOM返回的NODELIST集合

```js
// arguments对象
function foo() {
var args = Array.from(arguments);
// ...
}
```

### 扩展运算符 ...

1. 将空位转为undefined
2. 将某些数据结构转化为数组，比如类数组arguments
3. 主要还是用作函数的调用，将一个数组转化成参数序列
```js
console.log(...[1, 2, 3])  // 1 2 3
```
