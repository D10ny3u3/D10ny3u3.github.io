---
title: 3D pathology literatures
date: 2026-10-14
categories:
  - 3D pathology literatures
tags:
  - literature
---

# AI Cell Literature

A curated collection of papers on building 3D tumor pathology.

## Methods based on Serial Section 

- [CODA: quantitative 3D reconstruction of large tissues at cellular resolution | Nature Methods](https://www.nature.com/articles/s41592-022-01650-9) — 本文介绍了一种名为 CODA 的方法，该方法利用连续切片的苏木精-伊红染色组织切片，以亚细胞分辨率重建体积巨大（可达数立方厘米）的组织。我们展示了 CODA 在胰腺、皮肤、肺和肝脏组织中重建三维（3D）独特微观解剖结构的能力。

- [A vision–language foundation model for precision oncology | Nature](https://www.nature.com/articles/s41586-024-08378-w) — 本研究开发了基于统一掩码建模的多模态 Transformer（MUSK），这是一种视觉-语言基础模型，旨在利用大规模、未标注、非配对的图像和文本数据。MUSK 首先使用来自 11,577 名患者的 5000 万张病理图像和 10 亿个病理相关文本标记进行预训练，并利用统一掩码建模进一步使用 100 万个病理图像-文本对进行预训练，以有效地对齐视觉和语言特征。 MUSK 无需或只需极少的额外训练，即可在广泛的应用场景中接受测试，并在 23 项图像块级和切片级基准测试中展现出卓越的性能，包括图像到文本和文本到图像的检索、视觉问答、图像分类和分子生物标志物预测。

## Methods based on Computational Prediction

- [AI病理文摘 | Advanced Science: 用力学重建三维细胞世界，CellSqueeze3D将二维切片推向三维病理](https://mp.weixin.qq.com/s/AkgLgKZO0LTcvCMdexe0Hg) — 它利用细胞在组织中互相挤压的几何规律，从二维核分割反推出每个细胞的三维大小、深度与邻接关系，让二维切片第一次具备了“三维结构感”。更重要的是，这种虚拟三维不仅看起来合理，还能显著提升细胞类型判断、基因突变预测和预后分析，展现出真实的生物学价值。

- [Synthetic Generation of Three-Dimensional Cancer Cell Models from Histopathological Images](https://arxiv.org/html/2101.11600v2) — 我们提出了一种新的框架，该框架基于生成器-判别器模式生成合成三维组织学模型，优化约束特征，并通过 Blender 界面构建三维模型，利用生物样本特有的平滑形状连续性。为了捕捉整个细胞簇的空间上下文，我们部署了一种新型的深度拓扑转换器，该转换器在细胞群图像上实现注意力机制，以提取特征供冻结特征解码器使用。

- [Inferring a third spatial dimension from 2D histological images](https://ieeexplore.ieee.org/document/8363644) — 本文提出了一种方法，用于推断给定二维图像中染色剂在垂直于载玻片表面方向上的分布情况，从而获得组织的三维表示。该推断是通过在确保原始二维图像真实分解和重建的约束条件下分解染色浓度图来实现的。我们的研究表明，该方法能够生成逼真的三维图像，使其成为训练深度学习模型时数据增强的潜在工具。

## Data 

- [Combining spatial transcriptomics and ECM imaging in 3D for mapping cellular interactions in the tumor microenvironment](https://www.sciencedirect.com/science/article/pii/S2405471225000948) — 在此，我们将三维 ST 与 ECM 成像相结合，对来自一例临床肺癌的连续切片进行分析，系统地量化了 CN 中的分子状态、细胞间相互作用和 ECM 重塑。Raw and processed image-based ST and second harmonic imaging data generated in this study have been deposited at Zenodo (https://doi.org/10.5281/zenodo.7899173) and are publicly available as of the date of publication.

- [Cellular architecture and neighborhood-informedvirtual spatial tumor profiling from histopathology](https://www.cell.com/cell/fulltext/S0092-8674(26)00590-8) — 该研究通过41重CODEX空间蛋白组学技术，对457例非小细胞肺癌（NSCLC）患者的超1800万个细胞进行单细胞分辨率解析，首次系统定义了10种保守的细胞邻域（CN），构建虚拟肿瘤空间图谱；在此基础上，团队开发了基于病理大模型的AI平台CANVAS，可在常规H&E切片中精准预测这些空间结构，并在覆盖9种癌症类型的5000余例患者中验证了其预后分层与免疫治疗疗效预测价值。The CODEX data and matched H&E images generated in this study are deposited in Zenodo: https://zenodo.org/records/20263843. The CANVAS pipeline and analysis scripts are publicly available at GitHub: https://github.com/lilab-stanford/CANVAS.

## Review 

- [3D multi-omics tumour atlases: from technology to biology and clinical translation](https://www.nature.com/articles/s41568-026-00940-0) — The reviewed work emphasizes that understanding tumour evolution in 3D is essential for early interception, diagnosis, and treatment.
