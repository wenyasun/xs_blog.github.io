---
layout: post
title: Attention机制学习
author: Wenya
---
## 一个简单的小例子: attention for text
假设我们要对一个长度为10个词的sentence: X(10*100)进行attention, 每个词维度为100. 首先会计算10*10的attention score:<br> 
query matrix: 100*K, key matrix: 100*K <br>
X * query matrix * transpose(key matrix) * transpose(X)<br>
Attension probablity is computed afterwards as a softmax  of attention score times value: <br>
attention probalility(X)_t = softmax(i_th, attention score,:)*X*value,  where value is [100, d_out]
![](../images/2021-02-18-13-57-51.png)

## Attention for images
![](../images/2021-02-18-14-12-47.png)

Reference paper: 
<a href ="https://openreview.net/pdf?id=HJlnC1rKPB"> ON THE RELATIONSHIP BETWEEN SELF-ATTENTION AND CONVOLUTIONAL LAYERS </a>