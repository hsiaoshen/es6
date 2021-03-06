# DOM文档对象类型

整个文档全都由节点组成，包括元素(HTML标签)节点，文字节点，属性节点。


## document

文档的根节点:文档节点（document）

### document对象属性

1. document.documentElement:该属性指向html元素
2. document.body:该属性指向body元素
3. document.title:文档标题
4. document.URL:获取文档的完整的url，读
5. document.domain:取得域名,读写
***
用途:解决页面中子域之间的跨域通信问题

方法: 设置各自的domain一致

注意: 若是设置了document.domian，就不能再设置回原来的域名了
***
6. document.referrer:取得来源页面的url，读
7. hasFeature()：可以检测DOM功能是否该版本号支持，2个参数为功能和版本号

## 节点类型(nodetype属性判断)

1. Node.ELEMENT_NODE (1);  //nodeName为标签名，nodeValue为null
2. Node.ATTRIBUTE_NODE (2);
3. Node.TEXT_NODE (3);
4. Node.CDATA_SECTION_NODE (4);
5. Node.ENTITY_REFERENCE_NODE (5);
6. Node.ENTITY_NODE (6);
7. Node.PROCESSING_INSTRUCTION_NODE (7);
8. Node.COMMENT_NODE (8);
9. Node.DOCUMENT_NODE (9);
10. Node.DOCUMENT_TYPE_NODE (10);
11. Node.DOCUMENT_FRAGMENT_NODE (11);
12. Node.NOTATION_NODE (12)。
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
5. obj.hasChildNodes() --> 判断是否包含一或多个子节点，若是返回true
## 创建元素

var obj = document.createElement()

应用场景:对于不支持H5新标签的的，可以使用这个创建标签，然后赋予样式即可

## 添加元素

1. obj.appendChild(node) --> 在元素内部的末尾添加元素
2. obj.insertBefore(newnode, refnode), 将newnode节点插入到obj节点的refnode之前。若refnode为null,等同于appendChild

## 删除子元素

obj.removeChild(b)  --> 返回被删除的节点

## 替换节点

obj.replaceChild(newNode,oldNode) 

## 属性节点操作

1. node.getAttribute('class') -->获得class属性值
2. node.setAttribute('class','one')  /  node.className = 'one'(兼容写法)    --> 设置属性
3. removeAttribute("属性")   /  node.className=''(兼容写法)  //移除属性

注意:自定义的属性不会被getAttribute获取到

## 修改多个CSS属性

node.style.cssText = 'width:100px;height:100px;'

## 克隆节点

node.cloneNode(布尔值)

布尔值:
1. true:深度拷贝，拷贝所有子节点。
2. false:浅拷贝，只拷贝节点本身

## 文本节点 

### 特点
1. nodeType 的值为 3;
2. nodeName 的值为 "#text" ;
3. nodeValue 的值为节点所包含的文本;
4. parentNode 是一个 Element ;

### 操作

#### 创建文本节点

document.createTextNode() -- 参数为要插入节点的文本

可以为同一个元素节点添加多个文本节点，但是如果两个文本节点是相邻的同胞节点,那么这两个节点中的文本就会连起来显示,中间不会有空格。


## 使用DOM操作来添加动态js脚本或者动态样式表

```js
function loadScript(url){
var script = document.createElement("script");
script.type = "text/javascript";
script.src = url;
document.body.appendChild(script);  //一添加就会下载，所以封装利用函数调用
}
```
