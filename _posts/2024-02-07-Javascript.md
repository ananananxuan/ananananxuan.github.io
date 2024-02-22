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

```
while(true){
	let word = prompt("今天开心了吗？请回答开心或者不开心")
	if(word == "开心"){
	  break
	}
  }
```
⭐<br>
当明确循环次数的时候，一般用for<br>
当不明确循环次数的时候，一般用while<br>

<strong>for循环的嵌套 </strong>
```
for（外部声明记录循环次数的变量;循环条件；变量变化量）{
	for（内部声明记录循环次数的变量;循环条件；变量变化量）{
	}
}
```
```
for(let i = 1; i<=3;i++){
	document.write(`第${i}天<br>`)
	for(let j =1;j<=5;j++){
	  document.write(`记住了第${j}个单词<br>`)
	}
  }
  ```
<h3>十二、数组</h3>
array是一种可以按照顺序保存数据的数据类型<br>
可以用一个变量储存多个数据，数据类型可以是任意的<br>
1.声明数组的方法
```
let arr = [1,2,"hax"]
```
2.数组求和以及平均值
```
let arr = [2, 6, 1, 7, 4]
    let sum = 0
    for (let i = 0; i < arr.length; i++) {
      sum += arr[i]
    }
    document.write(`平均数是${sum / arr.length}`)
```
3.数组中的最大值和最小值
```
let arr = [2, 6, 1, 7, 4];
let min = arr[0];
for (let i = 1; i < arr.length; i++) {
  if (arr[i] < min) {
    min = arr[i];
  }
}
document.write(`最小值是${min}`)
```
4.数组的增
```
let arr=[]
arr[0]=1
arr[1]=2
arr.push()加在数组的末尾（一个或多个元素）
arr.unshif()加在数组的开头（一个或多个元素）
```

5.数组的改
```
let arr=[1,2,3]
arr[0]=2
```
6.所有元素的修改
```
let arr = [2, 6, 1, 7, 4]
    for (let i = 0; i < arr.length; i++) {
      document.write(arr[i]+'老师<br>')
    }
```
7.数组的筛选
```
let arr = [2, 6, 1, 7, 4]
    let arrnew = []
    for (let i = 0; i < arr.length; i++) {
      if(arr[i]>=5){
        arrnew.push(arr[i])
      }
    }
    document.write(arrnew)
```
8.数组的删除
```
arr.pop()删除最后一个元素，返回该元素的值
arr.shift()删除第一个元素，返回该元素的值
arr.splice(起始位置，删除几个元素）
```
9.冒泡排序
```
let arr = [5, 4, 3, 2, 1]
    let t = 0
    for (let i = 0; i < arr.length - 1; i++) {
      for (j = 0; j < arr.length - i - 1; j++) {
        if (arr[j] > arr[j + 1]) {
          t = arr[j]
          arr[j] = arr[j + 1]
          arr[j + 1] = t
        }
      }
    }
    document.write(arr)
```
or
```
arr.sort()
```

<h3>十三、函数</h3>
作用：抽取和封装

1.声明
```
function 函数名(){
	函数体
}
```
2.调用
```
函数名()
```
函数的特点：带小括号

3.函数的传参 形参
```
function 函数名(参数1，参数2){
	函数体
}
函数名(a,b)实参

function getSum(arr) {
      let s = 0
      for (let i = 0; i < arr.length; i++) {
        s += arr[i]
      }
      document.write(s)
    }
    getSum([1, 3, 4, 5])
    ```
4.函数的返回值
```
function getSum(arr) {
      let s = 0
      for (let i = 0; i < arr.length; i++) {
        s += arr[i]
      }
      return s
    }
    let sum = getSum([1, 3, 4, 5])
    document.write(sum)
```
找个变量等于返回值，再打印

5.作用域
定义：一段代码中所用到的名字并不总是有效和可用的，限定这个名字的可用性的代码范围就是这个名字的作用域。
作用域的使用提高了程序的逻辑的局部性，增强了程序的可靠性，减少了名字的冲突。<br>
全局变量 全局作用域 <br>
局部变量 局部作用域<br>
访问原则：在能够访问到的情况下，先局部，后全局。按照就近原则<br>

6.匿名函数(和具名函数相比较)
```
Function(){

 }
 ```
使用方式：<br>
①函数表达式，将匿名函数赋值给一个变量，通过变量名称进行调用
```
Let fn=function(){

}
②调用方式：fn()
```
不同点在于，匿名函数不能在声明函数之前调用
立即执行函数 <br>
防止代码污染，注意要加； 
```
(function(){
Let num = 10
})();

(function(){
Let num = 20
})();
(function(){}())；
``` 
7.逻辑中断
``` 
 function fn(x, y) {
      x = x || 0
      y = y || 0
      console.log(x + y)
    }
    fn()
    ``` 
相当于 形参里x=0，y=0
Console.log(false && i++)
后面的i++直接不执行
Console.log(11 && 22)
如果前后都是true，则返回最后一个真值

Console.log(true || i++)
后面的i++也不执行
Console.log(11 || 22)
如果前后都是true，则返回第一个真值

转换为布尔型
0、undefined、null、false、NaN、""转换为布尔型是false
其他都是true
隐式转换:
1.有字符串的加法“”+1，结果是“1”
2.减法-(像大多数数学运算一样)只能用于数字，它会使空字符串""转换为 0
3.null 经过数字转换之后会变为 0
4.undefined 经过数字转换之后会变为 NaN

对象object
是一种数据类型，是一种无序的数据集合,可以详细的描述某个事物


let obj = {
      uname: "hax",
      age: 26,
      gender: "female"
    }

1.声明对象
Let 对象名= {}
2.组成：属性和方法
属性：是特征
方法：功能和行为(函数)
3.对象的操作：增删改查
查找：对象.属性 进行访问 或者对象[`属性`]
改动：对象 .属性=新值
增加：对象.属性=新值
删除：delete 对象.属性
4.对象的方法

let obj = {
      uname: "hax",
      age: 26,
      gender: "female",
      sing: function(){
        console.log("冰雨")
      }
    }
在对象外面叫函数，在对象里面叫方法
对象.方法()
5.遍历对象
For in

let obj = {
      uname: "hax",
      age: 26,
      gender: "female",
      sing: function(){
        console.log("冰雨")
      }
    }
   for (let k in obj){
      document.write(obj[k])
    }
6.数组对象

let arr = [
      { uname: "hax", age: "26" },
      { uname: "lll", age: "22" }
    ]
for (let i = 0; i < arr.length; i++) {
      document.write([i].uname)
    }

7.内置对象
如Math
可去mdn上查找方法
包含的方法有：
random：生成0-1之间的随机数[0,1)
Ceil：向上取整
floor：向下取整
max：找到最大数
min：找到最小数
pow：幂运算
abs：绝对值
取0-10整数：

Math.floor(Math.random()*11)

生成N-M之间的随机数：

Math.floor(Math.random()*(M-N+1))+N
（可将其封装为一个函数）


function getNum(M, N) {
      return Math.floor(Math.random() * (N - M + 1)) + M
    }
    let num1 = getNum(1, 10)
    let flag = false  //开关变量
    while (true) {
      let num2 = +prompt("请猜一个1-10之间的整数：")
      if (num1 > num2) {
        alert("您猜小啦")
      } else if (num1 < num2) {
        alert("您猜大啦")
      } else {
        alert("您猜对啦")
        flag = false
        break
      }
    }
    if(flag){
      alert('您的次数用完啦')
    }


8.null是空对象


基本数据类型和引用数据类型
简单类型又叫做基本数据类型或者值类型，存储的是值，如str，number，Boolean，undefined，null，栈
复杂类型又叫做引用类型，存储的是地址，如object，array堆
