---
layout: mypost
title: Javascript
categories: [前端]
---
<h1>Javascript</h1> 

<h3>组成:ECMAscript+Web API(DOM+BOM)</h3>

<strong>ECMAscript:</strong>
规定了js基础语法的核心知识,包括:变量、分支语句、循环语句、对象

<strong>Web APIs:</strong>
DOM用于操作文档,对页面元素进行移动、大小、添加删除操作等； <br /> 
BOM用于操作浏览器,比如页面弹窗,检测窗口宽度、存储数据到浏览器。<br /> 

<h3>书写位置:</h3>

<h5>1.内联</h5> 
```
<body>
    <button onclick="alert('逗你玩~~')">点击我月薪过万</button>
</body>
```
<h5>2.内部(常用)</h5>
```
<body>
    <script>

    </script>
</body>
```

<h5>3.外部</h5>
```
<body>
    <script src=""></script>
</body>
```
<h3>js中的注释语句</h3>
<h5>单行注释</h5>
```
// 嘻嘻嘻嘻嘻嘻嘻嘻  快捷键ctrl+/
```
<h5>块注释</h5>

```
/* 嘻嘻嘻嘻嘻嘻嘻嘻*/  快捷键shift+alt+a
```
<h3>js中书写语句</h3>
<h5>输出语法</h5>
1.document.write
```
<script>
	document.write("xxxx")
	document.write("<h1>一级标题</h1>")
</script>
```
2.alert 页面弹出警示语句
```
<script>
	alert("一级标题")
</script>
```
3.控制台输出语句
```
console.log("xxx")
```
<h5>输入语法</h5>
1.prompt
```
<script>
	prompt("请输入您的年龄:")
</script>
```

<h3>声明变量</h3>
```
let age=18
age=19
```
```
let age=18,uname=“张三”
console.log(age, uname)
```

<h3>数组</h3>
array,一种将一组数据存储再单个变量名下的优雅方式
```
let arr = [小h,hh,hax]
console.log(arr)
console.log(arr[0])//取出数组元素
```
<h3>常量</h3>
用const声明的变量称为 常量
```
const pi = 3.14
```
<h3>数据类型:</h3>
<strong>基本数据类型</strong>
1.number数字型   整数,小数,正数,负数
2.string字符串型
3.boolean布尔型
4.undefined 未定义型
5.null 空类型

<h3>算术运算符</h3>
+-*/,取余数%  (作用就是判断一个数能不能被整除)<br>
NaN:not a number
<h3>字符串型</h3>
一般用'单引号'<br>
转义符\'你好\'<br>
'hello'+'word',字符串的连接方式<br>
'hello'+19 字符串和数值拼接可以把数值变成字符串<br>

<strong>模板字符串</strong>
```
let age = 19
`我今年${age}岁了`
```
<h3>布尔型</h3>

表示肯定或者否定的时候用布尔型。要么真要么假,真的是true,假的是false<br>

<h3>未定义类型 undefined</h3>
只声明没赋值就是undefined,因为js是弱数据类型
<h3>空类型</h3>
```
let obj = null 给对象赋值了,但是为空值
```
<h3>检测数据类型</h3>
```
typeof x
```
<h3>转换数据类型</h3>
1.隐式转换<br>
当+号前后有一个字符串就会把另一个也转换成字符串<br>
但+'123'会变成数值型,<br>
当-*/号前后有一个数值就会把所有的东西转换成数值<br>
<strong>+promp('请输入:')将输入的值转换成数值</strong>

2.显示转换<br>

转换成数字型 Number()<br>
只保留整数 parselnt() parseInt('12px')<br>
保留浮点数 parseFloat()





