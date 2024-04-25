---
layout: mypost
title: python小技巧
categories: [小技巧]
extMath: true
---

## 1.列表生成式
```
[i for i in range(10)]

[0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
```
    
## 2.匿名函数
```
    lambda x: x*x
    data.apply(lambda x: x*x)
```
        
## 3.日期转化
```
    date = pd.to_datetime(df['date'])
    date.year
    date.month
    date.day    
    date.weekday

```
## 4.字符串格式化
```
    ["你好{}".format(i) for i in range(5)]
  
```
格式说明符
```
    %s  #字符串
    %d  #整数
    %f  #浮点数
    %y  #年
    %m  #月
    %%  #文本百分比
    print("%s is %d years old" % ("Tom",20))

```
转义序列
```
    \n  #换行
    \t  #制表符
    \r  #回车
    \b  #退格
    \a  #响铃
    \v  #垂直制表符
    \'  #单引号
    \''  #双引号
    \\  #反斜杠

    fout.write("%s\t%s\n"%(curr_url,title))

```

    

  

## 5.面向对象

类->对象  
人类->小明

先将属性和方法封装在一个类中，再实例化对象，通过对象调用类的方法和属性

```
    class Cat:
        def __init__(self,name): #其中self指代实例化的对象本身·
            self.name = name #类实例化之后会自动调用初始化方法
        def eat(self):
            print(self.name + " is eating")
            
            
    cat1 = Cat("Tom") #创建对象，也就是类的实例化
    cat1.name #调用类中的属性
    cat1.eat() #调用类中的方法
```
类的继承，子类拥有父类的方法和属性，再封装一下子类特有的方法

```
    class MilkCat(Cat):
        
        def play(self):
            print(self.name + " is a crazy player")
            
    cat2 = MilkCat("Jerry")
    cat2.play()
```

子类继承父类时，当父类的方法不能完全满足子类的需求，可以先写一下新的方法，再通过super()调用父类的方法
```
class MilkCat(Cat):
        
        def eat(self):
            print("cats like milk")
            super().eat()
            
    cat2 = MilkCat("Jerry")
    cat2.play()
```

## 6.模块

以py结尾的文件，文件名就是模块名，模块可以包含函数、类、变量等。相当于工具包

```
    import 模块名  #也就以py结尾的文件的文件名
    from 模块名 import 函数名  #只导入模块中的某个函数

    模块名.函数名()  #调用函数
    模块名.变量名  #调用变量
    a = 模块名.类名()  #调用类
```
如果只从某一个模块导入一部分工具
```
    from 模块名 import 函数名,变量名,类名
    
    函数名()
    变量名
    a = 类名()
```
        
如果想要自己设计一个模块，在测试代码的时候，可以加上
```
    def main():
        函数名()
        a = 类名()
        变量名
        pass

    if __name__ == "__main__":
        main()
```
这样就不会在别人调用这个模块的时候执行测试代码了          

## 7.包
包是一个含有多个模块的特殊目录
包含有__init__.py＋其他模块(以.py结尾的文件)
在__init__.py文件中，指定对外界提供的模块列表
```
    from .模块1 import 函数名,变量名,类名 #这样才能调包的时候找到该模块

    from .模块2 import 函数名,变量名,类名
```

```
    import 包名 #可以将包里所包涵的模块全部导入
    import 包名.模块名  #只导入包里所包涵的模块
```
发布包
[压缩包发布包的视频操作指导](https://www.bilibili.com/video/BV1jt411L7zE?p=83&vd_source=917336f407022762079ae1d9a0b669fd)

## 8.文件

文件读写
```
    with open(文件名,模式) as 文件对象:
        文件对象.read()  #读取文件内容
        文件对象.write()  #写入文件内容
```

文件读写模式
```
    r  #读模式
    w  #写模式
    a  #追加模式
    rb  #二进制读模式
    wb  #二进制写模式

```

如果有文件则打开，没有文件则创建一个新文件
file = open("文件名",模式)
file.close()  #文件自动关闭

```
fout = open('output.txt','w',encoding='utf-8')
fout.flush() #刷新文件
fout.write('hello world')
fout.close()
```
## 9.os
```
import os
os.getcwd()  #获取当前工作目录 %pwd
os.chdir('路径')  #改变当前工作目录 %cd
os.listdir('路径')  #列出指定路径下的所有文件和文件夹 %ls -l
os.mkdir('路径')  #创建文件夹 %mkdir
os.rmdir('路径')  #删除文件夹 %rmdir
os.rename('原文件名','新文件名')  #重命名文件
os.remove('文件名')  #删除文件 %rm('文件名')
os.path.exists('路径')  #判断路径是否存在
os.path.join('路径','文件名')  #拼接路径 %join('路径','文件名')





