---
title: Explore Immune Scoring Systems
date: 2026-10-09
categories:
  - Bio-infomatics
tags:
  - literature
---

# CYT（cytolytic activity score，细胞溶解活性评分）

CYT（cytolytic activity score，细胞溶解活性评分）主要用于评估肿瘤组织中细胞毒性免疫反应的活跃程度，经典方法基于两个基因：GZMA（Granzyme A）和 PRF1（Perforin 1） 的表达量计算几何平均数[https://pmc.ncbi.nlm.nih.gov/articles/PMC8085935/; https://pmc.ncbi.nlm.nih.gov/articles/PMC4856474/; https://www.jci.org/articles/view/124108]。

## 1. CYT score 的计算公式

CYT=GZMA×PRF1\mathrm{CYT}=\sqrt{\mathrm{GZMA}\times\mathrm{PRF1}}CYT=GZMA×PRF1

其中，GZMA 和 PRF1 为同一样本中这两个基因的表达量。

* GZMA：编码颗粒酶 A。

* PRF1：编码穿孔素。

* CYT 越高，通常提示组织中的细胞毒性免疫活性越强，但不能单独证明肿瘤细胞实际发生了更多杀伤。

注意：计算时应使用同一种表达数据和统一的预处理方法；如果表达矩阵是 log 转换后的数据，不能不加区分地直接套用原始表达量的公式。

## 2. 这篇 JCI 文章具体怎么计算？

[https://www.jci.org/articles/view/124108]在 Methods 中明确写道：使用 PRF1 和 GZMA 的 normalized read counts 的几何平均数 计算 CYT score。

因此，严格按照这篇文章的方法：

CYT=PRF1norm×GZMAnorm\mathrm{CYT}=\sqrt{\mathrm{PRF1}_{norm}\times\mathrm{GZMA}_{norm}}CYT=PRF1norm×GZMAnorm

这里使用的是归一化后的 read counts，而不是直接使用原始 counts，也不是对两个基因分别进行 Z-score 标准化后取平均。

## 3. R 代码

假设 `expr` 是基因 × 样本的表达矩阵，且其中存储的是归一化后的非负表达量：

```{r}
cyt_genes <- c("GZMA", "PRF1")
cyt_expr <- expr[cyt_genes, , drop = FALSE]
cyt_score <- sqrt(
  cyt_expr["GZMA", ] * cyt_expr["PRF1", ]
)
cyt_score <- as.numeric(cyt_score)
names(cyt_score) <- colnames(expr)
```

注意： 如果你的 `expr` 是 `log2(normalized_count + 1)` 或其他 log 转换后的矩阵，不能直接使用上面这段代码。需要先确认表达矩阵的处理方式。

# Teff

这篇文章是 McDermott 等发表于 Nature Medicine 的 IMmotion150 研究，研究对象是转移性肾透明细胞癌，比较 atezolizumab、atezolizumab 联合 bevacizumab 与 sunitinib。文中使用了 T-effector/IFN-γ response（Teff）基因表达特征，用于评估肿瘤的免疫活化状态，并分析其与无进展生存期（PFS）的关系[https://www.nature.com/articles/s41591-018-0053-3 ]。

需要注意：Teff 是一个基因表达 signature 的评分，不是 CD8⁺ T 细胞的数量，也不是单纯的 IFNG 表达量。

## 1. Teff 评分包含哪些基因？

IMmotion150 的 Teff signature 包含 5 个基因[https://jitc.bmj.com/content/13/1/e010386; https://pmc.ncbi.nlm.nih.gov/articles/PMC7565517/]：

| 基因      | 主要生物学意义        |
| ------- | -------------- |
| `CD8A`  | CD8⁺ T 细胞相关标志  |
| `EOMES` | T 细胞效应分化相关转录因子 |
| `PRF1`  | 细胞毒性效应分子       |
| `IFNG`  | 干扰素 γ          |
| `CD274` | PD-L1，免疫调节相关分子 |

## 2. 具体怎么计算？

可以把计算过程分成两步：

1. 标准化基因表达值：对每个基因进行跨样本标准化，得到 z-score。

2. 汇总 5 个基因：计算这 5 个基因的 z-score *中位数*，作为每个样本的 Teff 评分。相关研究对 IMmotion150 signature 的描述支持这种计算方式[https://patents.google.com/patent/US20240410013A1/en; https://www.researchgate.net/publication/346731350_Molecular_Subsets_in_Renal_Cancer_Determine_Outcome_to_Checkpoint_and_Angiogenesis_Blockade]。

公式为：

Teffi=median⁡(ZCD8A,i,ZEOMES,i,ZPRF1,i,ZIFNG,i,ZCD274,i)\mathrm{Teff}_i = \operatorname{median}\left( Z_{CD8A,i}, Z_{EOMES,i}, Z_{PRF1,i}, Z_{IFNG,i}, Z_{CD274,i} \right)Teffi=median(ZCD8A,i,ZEOMES,i,ZPRF1,i,ZIFNG,i,ZCD274,i)

其中，Zg,iZ_{g,i}Zg,i 表示基因 ggg 在样本 iii 中标准化后的表达值。

注意： 这类评分依赖具体的表达预处理和标准化方式。若要严格复现原始论文，需要进一步核实原始 Methods 或补充材料中的表达预处理细节，不能仅凭公式认定不同数据平台可以直接比较绝对分值。

## 3. 如果你要用 R 计算

假设 `expr` 是基因 × 样本的表达矩阵，行名为基因名，列名为样本名，且表达值已经过适当预处理：

```{r}
teff_genes <- c("CD8A", "EOMES", "PRF1", "IFNG", "CD274")
teff_expr <- expr[teff_genes, , drop = FALSE]
teff_z <- t(scale(t(teff_expr)))
teff_score <- apply(teff_z, 2, median, na.rm = TRUE)
```

这里的 `scale()` 是按行标准化，所以每个基因分别在所有样本之间计算均值和标准差。

如果你想将它用于自己的 NanoString 数据，建议先确认原文的预处理方法，并保持所有样本使用一致的标准化流程。原研究的 Teff 分数与其他平台上自行计算的分数，不能直接套用相同的高低分阈值。

# T cell–inflamed GEP score

这篇文献是 Ayers 等发表于 Journal of Clinical Investigation 的研究：IFN-γ–related mRNA profile predicts clinical response to PD-1 blockade（2017）[https://www.jci.org/articles/view/91190]。文章建立了一个用于评估肿瘤免疫炎症状态的 18-gene T cell–inflamed gene expression profile（GEP）评分，并研究其与 pembrolizumab（抗 PD-1）治疗反应的关系。

最重要的一点是：原始 T cell–inflamed GEP 并不是简单统计 T 细胞标志基因的表达量，而是利用 18 个基因的表达构建多基因评分。 原文使用惩罚 Logistic 回归确定基因权重，并描述了用于计算签名分数的表达数据标准化流程。

## 1. 原文的计算方法

需要区分两种容易混淆的评分：

| 评分                                | 计算方法                                           |
| --------------------------------- | ---------------------------------------------- |
| Expanded immune 18-gene signature | 对标准化后、经 log⁡10\log\_{10}log10 转换的 18 个基因表达值取平均 |
| 最终 T cell–inflamed GEP            | 对 18 个基因的 housekeeping-normalized 表达值进行加权求和    |

T cell–inflamed GEP score 指第二种，即最终的加权评分。原文 Methods 明确说明，权重来自 elastic net 惩罚 Logistic 回归的最终回归系数。

### 具体计算步骤

## 1

获取 18 个基因的表达量。原研究使用 NanoString nCounter 对肿瘤组织的 RNA 进行检测。

## 2

Housekeeping normalization

对每个基因的表达计数取 log⁡10\log_{10}log10，再减去该样本 11 个 housekeeping genes 的平均 log⁡10\log_{10}log10 表达值：

Xig=log⁡10(Cig)−111∑h=111log⁡10(Cih)X_{ig}=\log_{10}(C_{ig})- \frac{1}{11}\sum_{h=1}^{11}\log_{10}(C_{ih})Xig=log10(Cig)−111h=1∑11log10(Cih)

其中，CigC_{ig}Cig 是样本 iii 中基因 ggg 的表达计数。

## 3

加权求和，得到最终 GEP score

GEPi=∑g=118wgXig\mathrm{GEP}_i=\sum_{g=1}^{18}w_gX_{ig}GEPi=g=1∑18wgXig

wgw_gwg 为原研究训练得到的回归系数。原文使用 5-fold cross-validation 选择惩罚参数，并通过多次随机分组确定最终基因集合与权重。

注意：上述公式中，表达计数应使用适合该检测平台的预处理结果；如果表达量为零，不能直接取对数，需要按照数据类型和预处理方案处理。

目前尚未找到公开的权重数据，退而求其次，按照 immune 18-gene signature 的逻辑进行计算。

```
{r}

gep18 <- c(
  "TIGIT", "CD27", "CD8A", "PDCD1LG2",
  "LAG3", "CD274", "CXCR6", "CMKLR1",
  "NKG7", "CCL5", "PSMB10", "IDO1",
  "CXCL9", "HLA-DQA1", "CD276", "STAT1",
  "HLA-DRB1", "HLA-E"
)

expr <- as.data.frame(expr)
present_genes <- intersect(gep18, rownames(expr))
gep_expr <- expr[present_genes, , drop = FALSE]

gep_log <- log10(gep_expr)
gep_score <- colMeans(gep_log, na.rm = TRUE)

gep_result <- data.frame(
  sample = colnames(gep_expr),
  immune_score = as.numeric(gep_score)
)

```

