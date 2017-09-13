# js事件

js中事件的三要素:事件源，事件，事件处理程序三部分组成

## 事件处理

### HTML事件处理

添加到HTML结构中

```html
<button onclick="alert('hello');">按钮</button>
```

## DOM0级

把函数赋值给一个事件处理程序

```js
obj.onclick = function(event){ ....};
```

### 常用的事件

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

## DOM2级

```js
obj.addEventListener('事件名'，'事件处理函数'，'布尔值')
obj.removeEventListener('事件名'，'事件处理函数'，'布尔值')
//true：捕获
//false：冒泡
```
