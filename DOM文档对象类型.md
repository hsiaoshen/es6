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



