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


## Encoder和Decoder

### Encoder

#### 1.输入部分
![encoder](encoders.png)

- Embedding
![embedding](embedding.png)

- 位置编码

Transformer相对于RNN来说，可以同时处理多个字/词。能够提高处理速度，但相对的也会忽略时间上的依赖关系。因此需要我们进行位置编码。

![position](position.png)
![image](image.png)

#### 2.多头注意力机制
- 基本注意力机制
Attention(Q,K,V)=softmax(QK^T/sqrt(d_k))V
![self-attention](self_attention.png)

- 在Transformer中如何操作
layer normalization


#### 3.前馈神经网络
输出的Z1和Z2经过Feed Forward再 Add & Normalize

![feed-forward](forward.png)


### Decoder
![decoder](decoder.png)


![encoder & decoder](image2.png)





