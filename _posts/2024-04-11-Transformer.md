---
layout: mypost
title: Transformer
categories: [深度学习]
extMath: true
---

注意力机制：在一堆信息中，更关注重点的信息，忽视无用的信息

注意力机制的计算公式：

Attention(Q,K,V)=softmax(QK^T/sqrt(d_k))V

其中Q,K,V是三个矩阵，Q(query)是查询，K(key)是键，V(value)是值，d_k是键矩阵的维度。

例如：Q是淘宝搜索框的输入，K是后台商品的关键字，QK^T表示相似性。V是产品在算法中的价值

softmax函数的计算公式：

softmax(x_i)=\frac{e^{x_i}}{\sum_{j=1}^{n}e^{x_j}}

具体例子：
https://zhuanlan.zhihu.com/p/48508221      
![self-attention](self_attention.png)
![self-attention](self_attention2.png)
详细解释：
![self-attention](self_attention3.png)

李宏毅b站课堂上的例子：
![self-attention](sa1.png)
![self-attention](sa2.png)


自注意力机制：


