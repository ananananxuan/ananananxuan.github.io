---
layout: mypost
title: python小技巧
categories: [小技巧]
extMath: true
---

## 1.列表生成式
```
b = [i for i in range(10)]
c = [i for i in range(30) if i % 3 == 0]
[0, 1, 2, 3, 4, 5, 6, 7, 8, 9]

b[0]
b[::2]
```
    
## 2.匿名函数
```
    lambda x: x*x
    data.apply(lambda x: x*x)

    x = lambda a, b : a * b
    print(x(5, 6))

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
    print("%.2f"%144.336)

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
class Cat:
    def __init__(self, name, age):
        self.name = name
        self.age = age
    def eat(self):
        print("{} is eating fishes".format(self.name))
    def __len__(self):
        return len(self.name)

class OrangeCat(Cat):
    def __init__(self, name, age, weight):
        super().__init__(name, age) #继承父类的一些属性
        self.weight = weight
        print("orangecat is so heavy with weight to %.1f"%self.weight)
    def __miao__(self):
        print("orangecat %s is miaomiao"%self.name)

diandian = OrangeCat("diandian", 3, 5)
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
        测试代码
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
    import 包名 #可以将包里所包含的模块全部导入
    import 包名.模块名  #只导入包里所包涵的模块
```
发布包
[压缩包发布包的视频操作指导](https://www.bilibili.com/video/BV1jt411L7zE?p=83&vd_source=917336f407022762079ae1d9a0b669fd)

## 8.文件

文件读写
```
    with open(文件名,模式,encoding='utf-8') as 文件对象:
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
os.listdir('路径')  #列出指定路径下的所有文件和文件夹 %ls
os.system('命令')  #执行系统命令 %run
os.mkdir('路径')  #创建文件夹 %mkdir
os.rmdir('路径')  #删除文件夹 %rmdir
os.rename('原文件名','新文件名')  #重命名文件
os.remove('文件名')  #删除文件 %rm('文件名')
os.path.exists('路径')  #判断路径是否存在
os.path.join('路径','文件名')  
```

## 10.jupyter notebook 中一些命令
在jupyter notebook中如果想执行在终端中才能执行的命令
可以使用
```
!python -V
!python hello_world.py
!python "../hello_world.py"

```
```
%%time #放在多行代码块的开始处，可计算这个单元格的运行时间

%run #相当于！python hello_world.py
```

如果代码太长了
可以用+ \ 换行写

## 11.字典
一个大括号，里面有很多不同的键值对
a = {'name':'Tom','age':20,'gender':'male'}

```
    a.get(键,默认值)  #如果键不存在，返回默认值
    a.keys()  #获取字典中所有的键
    a.values()  #获取字典中所有的值
    a.items()  #获取字典中所有的键值对
    a.pop(键)  #删除指定的键值对
    a.popitem()  #随机删除一个键值对

    pd.DataFrame([a]) #将字典转化为dataframe的方法

```
## 12.集合
集合是一个无序不重复元素的序列
a = {1,2,4,5,7}
```
    a.add(元素)  #添加元素
    a.remove(元素)  #删除元素
    a.clear()  #清空集合
    a.pop()  #随机删除一个元素
```

## 13.列表
列表是一个有序的元素序列
a = [1,2,3,4,5]
```
    a.append(元素)  #在列表末尾添加元素
    a.extend(列表)  #在列表末尾添加列表中的所有元素
    a.insert(索引,元素)  #在指定索引位置添加元素
    a.pop(索引)  #删除指定索引位置的元素
    a.remove(元素)  #删除指定元素的第一个匹配项
    a.clear()  #清空列表
    a.sort() #列表排序
    a.index(元素) #返回元素在列表中第一次出现的索引
    a.count(元素) #统计元素在列表中出现的次数
```

## 14.元组
元组是一个有序的元素序列
a = (1,2,3,4,5)
b = (1,)
```
    a.count(元素)  #统计元素在元组中出现的次数
    a.index(元素)  #返回元素在元组中第一次出现的索引
```

## 15.字符串
字符串是一个有序的字符序列
a = "hello world"
```
    a.count(子串)  #统计子串在字符串中出现的次数
    a.index(子串)  #返回子串在字符串中第一次出现的索引
    a.replace(旧子串,新子串,替换次数)  #替换字符串中的子串
    a.split(分隔符)  #将字符串按照分隔符分割成`列表`
    a.strip(字符)  #去除字符串两端的指定字符
```
## 16.随机数函数
```
import random
random.randint(a,b)  #生成a到b之间的随机整数
random.randrange(a,b,c)  #生成a到b之间以c为步长的随机整数
random.random()  #生成0到1之间的随机浮点数
random.uniform(a,b)  #生成a到b之间的随机浮点数
random.choice(列表)  #从列表中随机选择一个元素
random.shuffle(列表)  #将列表中的元素随机打乱

```
要注意下random模块和numpy中的不一样，numpy可以选择生成多少个
```
import numpy as np
np.random.randint(a,b,size)  #生成a到b之间size个随机整数
np.random.randrange(a,b,c,size)  #生成a到b之间以c为步长的size个随机整数
np.random.random(size)  #生成size个0到1之间的随机浮点数
np.random.uniform(a,b,size)  #生成a到b之间size个随机浮点数
np.random.choice(列表,size)  #从列表中随机选择size个元素
np.random.shuffle(列表)  #将列表中的元素随机打乱
```

