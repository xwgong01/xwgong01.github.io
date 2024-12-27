---
layout: post
title: LHAASO - LLM for Astrophsics Seminar Note
date: 2024-12-27 00:04 +0800
description: Recently I attended a meeting of IHEP LHAASO Collaboration and Zhejiang Lab. This is the note taken from the meeting
tags: ML
categories: Conference
---



## Why LLM? The tasks of LHAASO that asks for AI solutions

### Background Reduction
  - The gamma-ray background of LHAASO mainly consists of mis-classified cosmic rays. At present, LHAASO Collaboration reduces the background events by setting a threshold. Traditional method needs to perform a multi-dimensional optimization problem for each event in a 5-dimensional parameter space. This is not only time-consuming but also demands lots of computation resource. 
  - For KM2A, distinguishing gamma from protons is easier - gamma-ray air shower events produce mostly electron-positron pairs, while the latter is muon-rich. However, it's not easy to do this on WCDA, a result from the insensitivity for muons. More often, events are categorized by its morphology. Given that proton cascade produce more secondary particles moving in random direction, the cascade is more extended than gamma events. By measuring the dispersion of secondary particles from the core position, both proton and gamma events exhibit Gaussian-like distributions, with larger mean value for protons. Thus by setting a threshold and ignore all of the events with dispersion lareger than the threshold, high classification purity is achieved at the cost of lower selection efficiency. 
  <!-- - Thresh, divergence, core, nhit, direction 5-dimensional analysis -->
  <!-- - 目标： 降低背景2-5倍 -->
  <!-- - 提高significance -->
  - The goal of using AI tools is to reduce the cosmic ray background by a factor of 2-5. This might not be a great improvement for bright sources like crab, but for faint targets, i.e. flux equivalent to 0.01 crab, reducing background is of great importance in enhancing significance of detection. 
  
### Particle Categorization
 <!-- 粒子鉴别 -->
  - There are 26 different categories of cosmic ray particles, from H to Fe. Theoretically, these events have different location of cascade maxima, thus could be classified according to observations of WFCTA. This is however almost impossible in practise due to low quality of WFCTA imaging and the influence of cascade location and observation angle. 
  

### Noise Reduction
- Noise is quite common for both ED, MD and WCD. Assuming that secondary particles from a single event arrive at a flat surface in the space of x,y and t, noise outside this surface could be reduced. However, this will certainly exclude some signals, and noise in the surface is not distinguishable.  

### Event Reconstruction
- Event reconstruction is highly dependent on air shower simulations. Detector array can only do discrete sampling of signals. If AI tools can do some kind of "interpolation" but with prior knowledge from simulations, the reconstruction error will be smaller.

<!-- - 事例重建
  - 模拟加密/扩展探测器阵列，使用生成式AI生成探测器之外的Hits -->
<!-- 
- 多源解析
  - 重叠源的分析
  -  -->
### Multiple Source Analysis
- Near the milky way, source is dense and overlap, posing challenge to source identification. AI tools could help in analysis of source, resolving the contribution from each source. 

<!-- - 多探测器协同重建（km2a+wcda+wfcta）

- 探测器标定/模拟

- 天体源分析
  - 时变分析 -->

<!-- 
## WCDA背景排除介绍

Proton: more muon, more extended secondary particles

Gamma:  less muon, mainly electron-positron pairs

$$\mathcal{C} = \frac{N_{hit}}{C_{xPE}}$$
nhit / radius that contain most hits

PINCness: gamma with smaller PINCness (threshold)

## LHAASO联合观测成分鉴别

-  区分核子种类
   -  Xmax可以区分轻重元素： 轻元素xmax更靠下
   -  观测角度与WFCTA测量xmax距离有关
   -  变量连续，筛选出的数据很少
   -  几何重建精度影响分类准确率
-  多变量区分？
   -  难以有统一普适的变量构造
   -  现阶段变量
      - $$ Purity = N_p/(N_p + N_{heavy})|_{select}$$
      - $$Selection = N_{proton,select}/N_{proton,all} 
- 在某种纯度下，使用AI提升挑选效率 

## KM2A宇宙线成分鉴别

- 触发条件 400ns内20个探测器（ed/md）着火,筛选前后5000ns的数据
- 2.5khz，1TB/day
- 参数： EMparticle/Muon ratio, 
$$\log\frac{N_\mu}{N_e^{0.86}}$$
- ML
  -  作为图像，损失信息
  - 作为序列，有无序量
  - 作为Graph,图的结构无法改变
  - 粒子云： 抽象坐标，可携带其余额外信息
    - DGCNN-边特征提取
  - 

 -->

<!-- ## Zhejiang Lab 大模型在天文学的应用 -->
## Zhejiang Lab LLM Application to Astronomy


### 科学模型

困难：有监督的训练数据很少

生物大分子的研究，机器学习和冷冻电镜精度相差不大--可以先通过ai计算可信性再进行精确分析

### 为什么要做科学模型
《A new golden age of discovery》
-  帮助科学家获取知识
-  生成、标注大型数据集
-  模拟复杂实验并加速
-  建模复杂系统
-  大规模参数空间搜索
  
GPT - 1e12 参数

- ChatGPT的组成： GPT + Chat
- GPT 无监督模型
  - 噪声数据经过编码也可以帮助训练
  - GPT的任务是将数据编码
- Chat为有监督学习，（指令跟随）
- 基础模型与CPT,SFT...
  - 基础模型GPT,021,LLaMa等，将数据压缩编码
  - SFT， instruction model,指令模型
  - 或者GPT+CPT+SFT，CPT是领域模型（特化数据对基础模型进行微调），对特定领域进行优化
- 一般而言，基础模型的训练数据不包含最专业的数据 （语料库包含大量生物医药语料，不包含高能物理等），加入领域的语料进行基础模型的训练，形成领域模型。基础模型一般很宽泛
  
### 大模型为什么大
- 充分算力 -- GPU
- 大量数据,数据驱动--Token （B-T之间的数据规模）
- 基于模型 Transformer

- 科学基础模型+ 地学+天文（GeoGPT,AstroOne）能力迁移+ 科学工作空间

### 科学基础模型 
文理兼修，能成为未来科学家的辅助（大脑），然后开发工具（手脚）

1. 提出解决方法，将问题处理流程化
2. AI科学家，看到问题，提出问题

1+N模型（基准模型，多领域）->支撑领域专家模型（混合专家模型MOE）

### 科学基础模型-数据
1. 数据规模： 通用语料1e4B,科学数据（文本）匮乏（2e5篇论文只有130B）
2. 数据种类： 跨学科，多模态，多尺度
3. 数据对齐： 数据模态能够转化

### 科学基础模型--推理能力
多模态数据对齐增强
，知识图谱
，Q*算法
，外部工具辅助验证（模拟器，代码解释器等）

#### GeoGPT-地学语言模型
辅助地学科学家进行数据统计分析，知识整理等辅助性研究，从论文中抽取数据信息

300B领域语料，基于021科学基础模型，qwen等

#### 天文大模型
天文大语言模型 + 恒星光谱模型等科学模型

一个语言模型+ 图文解释模型 + 其余科学模型： 1+1+X

**同样面临无法验证的问题**

太阳耀斑活动预测（感觉可迁移至提升灵敏度）以及特征提取 （跨模态重构，太阳光学成像与磁场成像重构，郝奇组）




