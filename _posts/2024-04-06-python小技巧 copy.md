---
layout: mypost
title: python小技巧
categories: [小技巧]
extMath: true
---

## 1.列表生成式
```
[i for i in range(10)]
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
    "你好{}".format(i) for i in range(5)
  
```

