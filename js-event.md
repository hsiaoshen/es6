# js事件

js中事件的三要素:事件源，事件，事件处理程序三部分组成

## 事件流

### 概念

描述从页面中接受事件的顺序。

### 事件捕获

事件在最外层就被捕获，然后沿着DOM树依次向下传播到事件的实际

### 事件冒泡

事件从事件发生源一直向上传递

具体实现:IE9、Firefox、Chrome 和 Safari 则将事件一直泡会跳过 <html> 元素(从 <body> 直接跳到 document )冒泡到 window 对象

#### 阻止事件冒泡

### DOM事件流

先捕获然后在目标上触发，最后冒泡到document文档

## 事件处理

### HTML事件处理

添加到HTML结构中

```html
<button onclick="alert('hello');">按钮</button>
```

### DOM0级

把函数赋值给一个事件处理程序，被认为元素的方法，即该处理程序是在元素的作用域上进行的，也就是说this等于引用当前元素

```js
obj.onclick = function(event){ ....};
```
移除事件
```js
btn.onclick = null;
//删除事件处理程序
```


#### 常用的事件

事件名 | 事件说明
------|--------
onlick| 鼠标单击
ondbclick| 鼠标双击
onkeyup| 按下并释放键盘上的一个键时触发
onchange| 文本内容或下拉菜单中的选项发生改变
onfocus| 获取焦点
onblur| 失去焦点
onload| 文档加载事件
onunload| 网页关闭时
onsubmit| 表单提交
onreset | 重置表单时

### DOM2级

```js
obj.addEventListener('事件名'，'事件处理函数'，'布尔值')
obj.removeEventListener('事件名'，'事件处理函数'，'布尔值')
//true：捕获
//false：冒泡
```
### IE处理

```js
obj.attachEvent("on事件名", "事件处理函数")
obj.detachEvent("on事件名", "事件处理函数")
```
