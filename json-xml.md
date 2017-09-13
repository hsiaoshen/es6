# json 和 xML 

## json

### 含义

是一种轻量级的基于文本的交换格式，用来可读数据交换，网络媒体类型是application/json，编写格式简洁，一般用在服务器和 Web 应用程序之间传输数据。由于它可以在平台之间进行数据交换，兼容性高，所以用的多

### 语法

1. 键/值对形式
2. 使用大括号保存对象，每一个键值对之间使用逗号隔开

### 序列化和反序列化

序列化:将json数据转化为字符串形式进行传输

```js
str = JSON.stringify(obj);
```

反序列化:将json字符串转为json格式,json解析

```js
 var ret = JSON.parse(str);
```

## xml

### 含义

扩展标记语言 (Extensible Markup Language, XML) ，用于标记电子文件使其具有结构性的标记语言，可以用来标记数据、定义数据类型，是一种允许用户对自己的标记语言进行定义的源语言。是标准通用标记语言 (SGML) 的子集，非常适合 Web 传输。XML 提供统一的方法来描述和交换独立于应用程序或供应商的结构化数据。

### 格式

使用标签式写法

```js
var xmlStr = "<rss version='2.0'>" +
    "<student><name>lisi</name><age>10</age><hobby><one>learn</one><one>sleep</one></hobby><contact>" +
    "<f>3878376873</f><m>98948798479</m></contact><human>true</human></student></rss>";
```
### 解析

#### $.parseXML（）

```js
    var doc = $.parseXML(xmlStr);
    console.log(doc);//DOM对象
```

#### 使用DOMParser解析

```js
var parser = new DOMParser();
    doc = parser.parseFromString(xmlStr2, "application/xml");
    console.log(doc);
```

## json和xml对比

1. 冗余度:XML 比 JSON 冗余,因此对我们来说编写 JSON 会更快。
2. XML 被用来描述结构化数据,不包含数组;而 JSON 包含数组
3. json中通过eval()进行JSON数据的读取，返回对象
4. JSON的速度要远远快于XML。
5. json对数据的描述不如XMl
6. xml相对于json的是重量级的，本质是解析方式。JSON只提供整体解析方案，而这种方法只在解析较少的数据时才能起到良好的效果；XML提供了对大规模数据的逐步解析方案，这种方案很适合于对大量数据的处理。


