# DOM文档对象类型

整个文档全都由节点组成，包括元素(HTML标签)节点，文字节点，属性节点。

## 获取节点

### 获取对应元素的节点
1. document.getElementById(“id”) id 为标记的 #id
2. document.getElementsByTagName(“div”) 所有的div div
3. document.getElementsByClassName(“test”) 所有类名为 test
4. document.querySelector()
5. document.querySelectorAll()

### 获取指定元素的父节点

var parent = obj.parentNode

### 获取元素的兄弟节点

下一个兄弟:

兼容写法:var one = obj.nextElementSibling || obj.nextSibling(ie9以下)  

上一个兄弟:

兼容写法:var two = obj.previousElementSibling || obj.previousSibling(ie9以下)

### 获取父元素的子节点

1. obj.firstElementChild || obj.firstChild 
2. obj.lastElementChild || obj.lastChild
3. obj.childNodes  --> 所有包括文本节点（空格和换行）在内的子节点
4. obj.children --> 仅包含标签，所有浏览器都使用 

## 创建元素

var obj = document.createElement()

应用场景:对于不支持H5新标签的的，可以使用这个创建标签，然后赋予样式即可

## 添加元素

1. obj.appendChild(node) --> 在元素内部的末尾添加元素
2. obj.insertBefore(newnode, refnode), 将newnode节点插入到obj节点的refnode之前。若refnode为null,等同于appendChild

## 删除子元素

obj.removeChild(b)  --> 返回被删除的节点

## 节点属性操作

1. node.getAttribute('class') -->获得class属性值
2. node.setAttribute('class','one')  /  node.className = 'one'(兼容写法)    --> 设置属性
3. removeAttribute("属性")   /  node.className=''(兼容写法)  //移除属性


## 修改多个CSS属性

node.style.cssText = 'width:100px;height:100px;'

## 克隆节点

node.cloneNode(布尔值)

布尔值:
1. true:深度拷贝，拷贝所有子节点。
2. false:浅拷贝，只拷贝节点本身
