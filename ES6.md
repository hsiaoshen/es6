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
4. 数组的合并

```js
// ES5  
[1, 2].concat(more)  
// ES6  
[1, 2, ...more] 
```
5. 与解构复制结合进行数组生成,但是必须是最后一个参数要不就报错

```js
const [first, ...rest] = [1,2,3,4,5]
// first = 1
// rest = [2,3,4,5]
```
6. 把字符串转为数组

```js
[...'hello']  
// [ "h", "e", "l", "l", "o" ] 
```

## 函数的扩展

1. 可以给参数赋默认值，若没有传参就使默认值
2. 优点:简洁，便于阅读，便于维护和修改
3. 已经定义了的参数变量不需要再声明
4. 与解构赋值默认值结合使用

```js
function fetch(url, { body = '', method = 'GET', headers = {} })
{
console.log(method);
} f
etch('http://example.com', {})
// "GET"
fetch('http://example.com')
// 报错
```

## 对象的扩展

1. 属性的简洁表示

```js
var foo = 'bar';
var baz = {foo};
baz // {foo: "bar"}
// 等同于
var baz = {foo: foo};
```

2. 方法的简洁表示

```js
var birth = '2000/01/01';
var Person = {
name: '张三',
//等同于birth: birth
birth,
// 等同于hello: function ()...
hello() { console.log('我的名字是', this.name); }
};
```
