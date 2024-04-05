---
layout: mypost
title: RNN and LSTM
categories: [深度学习]
extMath: true
---

# RNN 循环神经网络
recurrent neural network (RNN)

网络会有一个循环的结构，使得每一次的网络结果都依赖于上一次的计算结果。也就是说，RNN 对于当前位置的计算不仅取决于当前的输入，也非常取决于过去的输出状态。这个设计使得RNN可以捕获到序列输入中的前后依赖关系，也被称为时序动力学行为

![RNN](RNN.png)

## 优点：可以处理长度可变的序列输入，因此非常符合处理语言这类序列型的数据。

## 缺点：  
前面的信息在传递到后面的同时，信息权重下降，导致重要信息丢失
1. 梯度消失
2. 梯度爆炸
3. 训练困难

![RNN](disadvantage.png)
 

## 应用场景
![RNN](RNN application.png)
![RNN](RNN application2.png)

# LSTM 长短期记忆

LSTM 是一种特殊的 RNN，可以解决梯度消失和梯度爆炸的问题。
long short-term memory (LSTM)

LSTM 是一种特殊的 RNN，可以解决梯度消失和梯度爆炸的问题。