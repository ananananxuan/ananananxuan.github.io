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








# Transformer 流程

## tokenizer 切词器
![tokenizer](tokenizer.png)

可以从Hugging Face的Tokenizer库中找到


具体代码
```
from tokenizers import (
  models,
  normalizers,
  pre_tokenizers,
  trainers,
  Tokenizer,
)

tokenizer = Tokenizer(models.WordPiece(unk_token="[UNK]"))
# 切词，并把字典中没有出现的字转化成[UNK]

tokenizer.normalizer = normalizers.Sequence([normalizers.NFD(), normalizers.Lowercase()]) # 统一转换为小写,NFD是Unicode Normalization Form D

# 添加预处理分词器
tokenizer.pre_tokenizer = pre_tokenizers.WhitespaceSplit()# 按照不可见字符进预拆分

special_tokens = ["[UNK]", "[SEP]", "[PAD]", "[CLS]","[MASK]"] # 添加特殊字符

trainer = trainers.WordPieceTrainer(vocab_size=10000, special_tokens=special_tokens) # 训练模型

tokenizer.train(['./train.txt'], trainer=trainer)
tokenizer.save("./tokenizer.json")
```

这样就可以实现丢进去训练数据，对训练数据文本进行切词，且给每个词一个编码，类似于字典

接着调用我们训练好的模型
```
from tokenizers import Tokenizer

tokenizer = Tokenizer.from_file("./tokenizer.json")

# 输入文本
text = "你好，世界！"

# 编码
encoded = tokenizer.encode(text)

# 解码
decoded = tokenizer.decode(encoded.ids)

print(encoded.ids, decoded)
```


## 数据预处理

### 1.数据清洗