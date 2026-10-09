---
title: Explore Immune Scoring Systems
date: 2026-10-09
categories:
  - Bio-infomatics
tags:
  - literature
---

# CYT（cytolytic activity score，细胞溶解活性评分）

CYT（cytolytic activity score，细胞溶解活性评分）主要用于评估肿瘤组织中细胞毒性免疫反应的活跃程度，经典方法基于两个基因：GZMA（Granzyme A）和 PRF1（Perforin 1） 的表达量计算几何平均数。

![](https://www.google.com/s2/favicons?domain=https://pmc.ncbi.nlm.nih.gov\&sz=32)

PMC

+1

## 1. CYT score 的计算公式

CYT=GZMA×PRF1\mathrm{CYT}=\sqrt{\mathrm{GZMA}\times\mathrm{PRF1}}CYT=GZMA×PRF1

其中，GZMA 和 PRF1 为同一样本中这两个基因的表达量。

* GZMA：编码颗粒酶 A。

* PRF1：编码穿孔素。

* CYT 越高，通常提示组织中的细胞毒性免疫活性越强，但不能单独证明肿瘤细胞实际发生了更多杀伤。

注意：计算时应使用同一种表达数据和统一的预处理方法；如果表达矩阵是 log 转换后的数据，不能不加区分地直接套用原始表达量的公式。

## 2. 这篇 JCI 文章具体怎么计算？

你给出的文章在 Methods 中明确写道：使用 PRF1 和 GZMA 的 normalized read counts 的几何平均数 计算 CYT score。

![](https://www.google.com/s2/favicons?domain=https://www.jci.org\&sz=32)

JCI

因此，严格按照这篇文章的方法：

CYT=PRF1norm×GZMAnorm\mathrm{CYT}=\sqrt{\mathrm{PRF1}_{norm}\times\mathrm{GZMA}_{norm}}CYT=PRF1norm×GZMAnorm

这里使用的是归一化后的 read counts，而不是直接使用原始 counts，也不是对两个基因分别进行 Z-score 标准化后取平均。

## 3. R 代码

假设 `expr` 是基因 × 样本的表达矩阵，且其中存储的是归一化后的非负表达量：

R

```
cyt_genes <- c("GZMA", "PRF1")

cyt_expr <- expr[cyt_genes, , drop = FALSE]

cyt_score <- sqrt(
  cyt_expr["GZMA", ] * cyt_expr["PRF1", ]
)

cyt_score <- as.numeric(cyt_score)
names(cyt_score) <- colnames(expr)
```

注意： 如果你的 `expr` 是 `log2(normalized_count + 1)` 或其他 log 转换后的矩阵，不能直接使用上面这段代码。需要先确认表达矩阵的处理方式。

另外，CYT score 与你之前计算的 18-gene T-cell-inflamed GEP score 不同：CYT 只使用 GZMA、PRF1 两个基因，GEP 则综合 18 个免疫相关基因。两者反映的免疫特征有所重叠，但不能互相替代。
