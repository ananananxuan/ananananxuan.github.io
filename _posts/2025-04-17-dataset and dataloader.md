---
layout: mypost
title: dataset and dataloader
categories: [深度学习]
---


dataset 数据集

作用：
储存数据集的信息，__init__ self.xxx
获取数据集长度，__len__
获取数据集特定条目的内容，__getitem__

数据：
images = [[f'image{i}',i ]for i in range(10)]
```
class ImageDataset:
    def __init__(self, raw_data):
        self.raw_data = raw_data

    def __len__(self):
        return len(self.raw_data)

    def __getitem__(self,index):
        image, label = self.raw_data[index]
        return image, label

```


dataloader 数据加载器
作用：
从数据集随机加载数据，并拼接为一个batch
实现迭代器，迭代获取数据内容
```
class ImageDataLoaer:
    def __init__(self, dataset, batch_size):
        self.dataset = 
        self.batch_size = batch_size
    
    def __iter__(self):
        self.indexs = np.arrange(len(self.dataset))
        self.cursor = 0
        np.random.shuffle(self.indexs)
        return self

    def __next__(self):
        begin = self.cursor
        end = self.cursor + self.batch_size

        if end >= len(self.dataset):
            raise StopIteration()