---
layout: mypost
title: Javascript
categories: [前端]
---

<h1>Javascript</h1> 
<h3>一、组成:ECMAscript+Web API(DOM+BOM)</h3>

<strong>ECMAscript:</strong>
规定了js基础语法的核心知识,包括:变量、分支语句、循环语句、对象

<strong>Web APIs:</strong>
DOM用于操作文档,对页面元素进行移动、大小、添加删除操作等; <br /> 
BOM用于操作浏览器,比如页面弹窗,检测窗口宽度、存储数据到浏览器。<br /> 

<h3>二、书写位置:</h3>

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
<h3>三、js中的注释语句</h3>
<h5>1.单行注释</h5>
```
// 嘻嘻嘻嘻嘻嘻嘻嘻  快捷键ctrl+/
```
<h5>2.块注释</h5>

```
/* 嘻嘻嘻嘻嘻嘻嘻嘻*/  快捷键shift+alt+a
```
<h3>四、js中书写语句</h3>
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

<h3>五、声明变量</h3>
```
let age=18
age=19
```
```
let age=18,uname=“张三”
console.log(age, uname)
```

<h3>六、数组</h3>
array,一种将一组数据存储再单个变量名下的优雅方式
```
let arr = [小h,hh,hax]
console.log(arr)
console.log(arr[0])//取出数组元素
```
<h3>七、常量</h3>
用const声明的变量称为 常量
```
const pi = 3.14
```
<h3>八、数据类型:</h3>
<strong>基本数据类型</strong> <br>
1.number数字型   整数,小数,正数,负数<br>
2.string字符串型<br>
3.boolean布尔型<br>
4.undefined 未定义型<br>
5.null 空类型<br>

<h3>1.数字型基本运算</h3>
+-*/,取余数%  (作用就是判断一个数能不能被整除)<br>
NaN:not a number
<h3>2.字符串型</h3>
一般用'单引号'<br>
转义符\'你好\'<br>
'hello'+'word',字符串的连接方式<br>
'hello'+19 字符串和数值拼接可以把数值变成字符串<br>
<em>模板字符串</em>
```
let age = 19
`我今年${age}岁了`
```
<h3>3.布尔型</h3>

表示肯定或者否定的时候用布尔型。要么真要么假,真的是true,假的是false<br>

<h3>4.未定义类型 undefined</h3>
只声明没赋值就是undefined,因为js是弱数据类型
<h3>5.空类型</h3>
```
let obj = null 给对象赋值了,但是为空值
```
<h3>九、检测数据类型</h3>
```
typeof x
```
<h3>十、转换数据类型</h3>
1.隐式转换<br>
当+号前后有一个字符串就会把另一个也转换成字符串<br>
但+'123'会变成数值型,<br>
当-*/号前后有一个数值就会把所有的东西转换成数值<br>
<em>+promp('请输入:')将输入的值转换成数值</em>

2.显示转换<br>

转换成数字型 Number()<br>
只保留整数 parselnt() parseInt('12px')<br>
保留浮点数 parseFloat()

3.运算符<br>

①赋值运算符 = +=<br>

②一元运算符 <br>
++number先参与运算后变<br>
number++先变后参与运算 <br>
i++变量加一(计数的时候使用)<br>
i--让变量减一 <br>

③比较运算符:<br>

== 比较数据大小是否相等 <br>
! = =判断两边的值是否相等<br>
= = =判断数据类型和值是否相等<br>
NaN不等于任何值包括他自己<br>

④逻辑运算符 
```
and&&   or||   not <br>
```
运算符优先级
```
()>++ -- ! > */ > == > && >|| <br>
```
<h3>十一、表达式和语句</h3>

表达式可被求值<br>
语句不一定有值,如alert() 和console.log()<br>

<h4>1.分支语句</h4>

if分支语句<br>
三元运算符<br>
switch语句<br>

if语句:<br>
单分支
双分支
多分支

①单分支<br>
```
if(条件){
执行的代码
}
\\条件为true执行代码,否则不执行
\\除了0,所有的数字都为真
```

②双分支:<br>
```
if(条件){
执行代码1
}else{
执行代码2
}
```
③多分支:<br>
```
if(条件1){
执行代码1
}else if(条件2){
执行代码2
} else{
执行代码3
}
```
2.三元运算符(一般用来执行取值操作)

条件?满足条件执行代码1:不满足条件执行代码2 
```
let ddd = 3 < 5 ? 5 : 3
```

3.switch语句
```
switch(数据){
	case 值1:
		  代码1
		  break
	case 值2:
		  代码2
		  break
	default:
			代码n
			break
}
```
⭐<br>
if ……else平常用的较多<br>
switch case多用确定的值<br>

当分支比较少的时候用if……else<br>
当分支多(>5)的时候用switch效率更高,结构更清晰<br>

<em>断点调试</em>
源代码中打断点

<h4>2.循环结构</h4>
实现一段代码的重复执行<br>

<strong>①while循环</strong>
重复执行一些操作<br>
```
while(循环条件){

要重复执行的代码

}
```
<em>while循环的三要素:</em> <br>
变量起始值<br>
终止条件<br>
变量变化量<br>
```
let num = +prompt("请输入重复次数:")
let i = 1
while(i<=num){

      document.write("月薪过10w<br>")

      i++
}
```
<em>循环退出</em>
break 结束所有循环<br>
continue 结束本次循环,重新判断条件进行下一次<br>
```
if(条件) {
break
}
```

<strong>②for循环</strong>

```
for(起始条件;终止条件;变量变化量){
代码
}
```
⭐for循环最大的价值:遍历数组
```
for(let I =0;i<=3;i++){
	Document.write(arr[i])
	}
	
```
终止条件
```
i<=arr.length-1或者i<arr.length
```
while(true)可用来构造无限循环的案例,使用break来退出循环<br>
for(;;)用来构造无限循环<br>












