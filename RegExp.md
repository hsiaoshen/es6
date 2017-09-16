# 正则表达式

## 创建正则表达式

1. var pattern = /test/g;
2. var patterns = new RegExp('hello','g');
3. var patterns = new RegExp(/hello/g);

## 常用方法

### exec

pattern.exec(str)

返回一个数组

全局模式下:每次执行都会返回一个匹配项，但会改变lastIndex值，下次执行从lastIndex位置进行匹配

非全局模式下:无论多少此执行都只会返回第一个匹配项，lastIndex也不会改变

### replace

str.replace(pattern,newstr)

返回一个被替换过的新的字符串

## 匹配模式

1. . [^\n\r]  -------除了换行和回车之外的任意字符
2. \d [0-9]    --------   数字字符
3. \D [^0-9]   -------  非数字字符
4. \s [ \t\n\x0B\f\r] ------ 空白字符
5. \S [^ \t\n\x0B\f\r]  ------   非空白字符
6. \w [a-zA-Z_0-9]   ------      单词字符
7. \W [^a-zA-Z_0-9]  ------     非单词字符 
8. * ------重复零次或更多   (>=0)
9. +  ------   重复一次或更多次  (>=1)
10. ?  ------   重复零次或一次   （0||1）  要么有 要么没有
11. {} ------   重复多少次的意思   可以有多少个  
12. {n} ------  n次
13. {n,} ----- 重复n次或更多  (x>=n)
14. {n,m} ------重复出现的次数(n<=x<=m)
15. a|b  ------  一个 a或者b  

注意:当　* 和　+ 后边添加？时可以进行最短匹配。