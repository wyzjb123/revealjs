# 基于Transformer模型的社交评论筛查
<br/>
<br/>
<br/>
<br/>
<br/>

# 钟佳滨 
--

## Overview

<div class="font-self">本次论文答辩的主要内容</div>

- 论文的选题背景和意义
- Transformer模型的结构及选择原因
- 本文使用的BERT模型介绍
- 模型训练的过程及效果展示
---

<div class='title'>论文的选题背景和意义</div> 
--

## 选题背景及意义
<div class="font-self" id='key'>选择论文题目的原因</div>

- ~~因为选择AI方向~~因为Transformer模型在自然语言处理的优势
- 社交媒体评论较多数据量大
- 选择微博平台因为数据集较多数据好收集

<div class="font-self" id='key' >选题意义</div>

+ 有了情感分类的标签可以做许多的下游任务
+ 评论内容筛查的结果可以做情感分析
  - 将不同情感的评论数进行统计得出情感倾向
+ 将不好的负面评论可以做出屏蔽
  - 将负面的评论可以选择性的关闭
---

<div class='title'>Transformer模型的结构及选择原因</div> 

--

## Transformer模型结构
<div class="font-self">什么是Transformer?</div>

<blockquote><div class="font-self">
A transformer is a deep learning model that adopts the mechanism of self-attention, differentially weighting the significance of each part of the input data.<br>
<div class='cite'>————《Wikipedia》</div></div></blockquote>

~~变形金刚？变压器？~~ [(新的模型结构)](https://arxiv.org/pdf/1706.03762.pdf)
- 拥有编码器解码器的架构
- 使用<red>自注意力机制</red>作为模型的基础
- 对序列模型的输入只有长度要求，输出可以是任意
--
## Transformer模型结构
<div class="font-self">模型结构图</div>
<img src="static\img\dot-attention.svg" class="right-picture">
<img src="static\img\first-input.gif" width=600px height=300px margin=0px>

- 初始化三个矩阵Q、K、V假设为4*3的矩阵和输入向量4\*1的向量
- 将输入向量与三个初始化矩阵相乘得到图中对应的三个矩阵输入
--
## Transformer模型结构
<div class="font-self">通过KQ<div>
<img src="static\img\attention-score.gif" width=600px height=300px margin=0px>

$$ Attention(Q,K,V)=Softmax(\tfrac{QK_{}^{T}}{\sqrt{dk}})V $$


