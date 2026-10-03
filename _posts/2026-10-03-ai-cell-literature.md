---
title: AI Cell Literature
date: 2026-10-03
categories:
  - AI Cell Literature
tags:
  - literature
---

# AI Cell Literature

A curated collection of papers on artificial intelligence
for cellular and tissue biology.

## Perspectives 

- [AI虚拟细胞提出者最新Nature论文，推出“虚拟组织”模型，实现超越单细胞，直达人体临床的跨尺度解析](https://mp.weixin.qq.com/s/p16dtROtBKEzee9XuqVZ5Q) — 2024 年 12 月 12 日，Charlotte Bunne 等人在 Cell 期刊发表了题为：How to build the virtual cell with artificial intelligence: Priorities and opportunities 的展望文章，提出了人工智能虚拟细胞（AI Virtual Cell，简称为 AIVC）概念，并为 AIVC 的构建提供了一个愿景，阐述了构建 AIVC 的机遇和挑战。

- [Cell：邢波/宋乐提出「虚拟细胞世界模型」（VCWM），给虚拟细胞装上操作系统](https://mp.weixin.qq.com/s/WcPggT6p_WvEQUvmk2F9Lg) — 2026 年 8 月 13 日，GenBio AI 公司联合创始人邢波教授和宋乐教授等在 Nature Medicine 期刊发表了题为：How to build an AI-driven digital organism 的展望文章，文章提出了一个更宏大的愿景——构建“AI 数字生命体”（AIDO），这是一个模块化、可连接且整体化的多尺度基础模型系统，利用 AI 来建模和模拟生物学与生命过程。细胞是其中一个尺度，而 AI 虚拟细胞（AIVC）只是 AIDO 的一个子集。2026 年 9 月 17 日，邢波教授和宋乐教授在 Cell 期刊发表了题为：A world model of the virtual cell 的展望文章，提出了“世界模型”（World Model）作为实现“AI 数字生命体”（AIDO）这一愿景的操作框架，不把细胞当成待预测的黑箱，而把它当成一台有状态、可干预、会演化的系统，即虚拟细胞世界模型（Virtual Cell World Model，VCWM）。在此框架下，VCWM 表示一个持续存在的细胞状态，并模拟其在基因、化学、环境及其他生物干预下的演化过程。

- [如何构建虚拟细胞，西湖大学郭天南团队最新Nature](https://mp.weixin.qq.com/s/CLxab2ZzB5t3lUXrJ-HZSg) — 7月1日，西湖大学医学院郭天南团队联合多家国际国内研究机构在Nature发表了一篇关于虚拟细胞构建路径的述评文章。文章总结了西湖大学组织的多次国际研讨会的思想碰撞成果，提出一套构建虚拟细胞的系统性理论框架，旨在通过AI建立能够理解、模拟、预测细胞行为并实现理性重设计的AI智能体系统。文章以酵母为例，但是这套理论框架也可以适用于人体、动物、植物、微生物等各类细胞。

## Computational Pathology

- [Cell ｜ 斯坦福团队构建“虚拟空间肿瘤”图谱，仅依靠H&E染色切片，即可还原肿瘤微环境空间生态信息](https://mp.weixin.qq.com/s/L6NmTvPHEWRgETUiIIBg5w)近期，Cell发表了关于肿瘤微环境空间架构与临床转化应用的重磅研究"[Cellular architecture and neighborhood-informedvirtual spatial tumor profiling from histopathology](https://www.cell.com/cell/fulltext/S0092-8674(26)00590-8)"。该研究由斯坦福大学医学院团队领衔，联合Broad研究所、MD安德森癌症中心等机构，通过41重CODEX空间蛋白组学技术，对457例非小细胞肺癌（NSCLC）患者的超1800万个细胞进行单细胞分辨率解析，首次系统定义了10种保守的细胞邻域（CN），构建虚拟肿瘤空间图谱；在此基础上，团队开发了基于病理大模型的AI平台CANVAS，可在常规H&E切片中精准预测这些空间结构，并在覆盖9种癌症类型的5000余例患者中验证了其预后分层与免疫治疗疗效预测价值。该研究突破了空间蛋白组学临床转化的瓶颈，为精准肿瘤学提供了可大规模部署的空间分析新范式。

- [提出“AI虚拟细胞”的团队，现在要虚拟整块组织了](https://mp.weixin.qq.com/s/dlyEoF1WbawMplHlsEE78Q) ；[虚拟细胞之后，Nature发布虚拟组织——实现空间蛋白跨尺度突破，为空间组学生态提供跨队列解决方案](https://mp.weixin.qq.com/s/QsWnwbRbKBrkiVZ_UaHpkw) —  [刚刚](https://mp.weixin.qq.com/s/SFSKlXrn8nDJA9ll2ieRuA)。空间蛋白质组学技术彻底改变了我们对癌症复杂组织结构的理解，但也给计算分析带来了独特的挑战 。每项研究都使用不同的标记物组合和实验方案，而且大多数方法都针对单一队列进行定制，这限制了知识迁移和稳健的生物标志物发现。本文介绍了虚拟组织（VirTues），这是一个通用的空间蛋白质组学基础模型，它能够直接从多重成像数据中学习蛋白质、细胞、微环境和组织的标记感知多尺度表征。[VirTues](https://www.nature.com/articles/s41586-026-10884-y) 基于单一预训练主干模型，支持标记物重建、细胞分割和分型、微环境注释、空间生物标志物发现和患者分层，包括跨异构标记物组合和数据集的零样本注释。在三阴性乳腺癌中，VirTues 衍生的生物标志物可预测抗 PD-L1 化疗免疫疗法反应，并在独立队列中对无病生存期进行分层，其性能优于从相同数据集和当前临床分层方案中衍生的最先进生物标志物。

- [Cell、Nature Medicine等顶刊连发5篇，虚拟肿瘤微环境正在成为新赛道](https://mp.weixin.qq.com/s/8F3BDHtJvqe8qDFjiQ5gbw) — 这5项研究关注的是同一个实际问题：空间蛋白组能够同时保留细胞身份和空间位置，但成本较高、通量有限；常规H&E切片数量多、临床资料完整，却不能直接测量蛋白表达。研究团队因此尝试利用配对数据训练模型，将少量空间蛋白组样本中获得的信息扩展到大规模H&E队列。不同研究选择了不同的预测目标。HistoPlexer从**H&E生成11通道虚拟蛋白图像**；Dayao等人利用空间蛋白组提供细胞标签，进而**在H&E中识别细胞类型**；HEX预测40个蛋白标志物，并用于肺癌预后和免疫治疗反应分析；GigaTIME将模型应用于14256名真实世界患者；**CANVAS**则从H&E预测细胞邻域和肿瘤空间生态型。

## Cell Trajectory

- [Nature Communications：单细胞“静态照片”，也能反推出细胞命运的动力学？](https://mp.weixin.qq.com/s/Um73DQFGq2KsVC0Mgek6jQ) — [Nature Communications](https://www.nature.com/articles/s41467-026-73257-z) 这篇论文提出的 DynNet，正是为了解决这个问题。它的全称是随机动力学推断网络。简单说，DynNet 想做的不是再画一条更漂亮的拟时序轨迹，而是要从多时间点单细胞 RNA 测序数据中，重建细胞状态演化的随机动力学模型、稳定状态、命运吸引子、转变路径、转变概率和关键调控基因。


## Virtual cell Intefering

- [虚拟细胞迎来自己的“大力出奇迹”：扰动预测第一次服从scaling law](https://mp.weixin.qq.com/s/ro0warAIpiLlo_3qfTwY0Q) — 一个核心问题：给细胞一个扰动（敲降一个基因、加一种药），它的基因表达会变成什么样？这个问题直接等价于药物研发的灵魂三问——靶点在哪里、药有没有效、为什么对这类细胞有效对那类无效。2026年3月，一篇bioRxiv预印本给出的答案，让整个领域为之一振：它第一次证明了，扰动预测这件事，也服从LLM式的scaling law——“大力出奇迹”在虚拟细胞里成立了。DOI:10.64898/2026.03.18.712807

- [Predicting cellular responses to perturbation across diverse contexts with State](https://www.cell.com/cell/fulltext/S0092-8674(26)00921-9)  — 近日，Cell上线了一篇由美国Arc Institute主导完成的研究"Predicting cellular responses to perturbation across diverse contexts with State"。Arc Institute近年来持续在功能基因组学与AI交叉领域发力，这项工作正是其虚拟细胞研究方向的又一力作。这项工作在方法与评估体系上的突破，[为后续虚拟细胞模型的开发奠定了重要基础](https://mp.weixin.qq.com/s/ITWyoFKrn3RA2Mk-cRbu-Q)。

- [Nature | 郭天南团队开发具备临床应用潜力的虚拟细胞垂类模型](https://mp.weixin.qq.com/s/q4sL0bdRbX6oQ81o_faNfg) — 2026年9月9日，西湖大学医学院、生命科学学院、西湖实验室郭天南团队联合北京大学、北京科学智能研究院、哈尔滨医科大学等科研机构，在Nature发表题为“An operational perturbation proteomics-based virtual cell model”的研究论文。他们开发了一款具有临床应用潜力的虚拟细胞模型 ProteinTalks，用于三阴性乳腺癌的药物疗效预测、肿瘤耐药靶点挖掘并个性化精准治疗指引。该研究展示了一条不同于单纯扩大数据和模型规模的新路径：以真实、连续的蛋白质动态为基础，构建了一个具有一定临床应用潜力的虚拟细胞垂类模型。

- [专题十六 | 虚拟细胞的构建与应用](https://mp.weixin.qq.com/s/kHd-0OtAMxPDZDirViY7MA) — 本期内容将聚焦近年来人工智能赋能单细胞与空间组学研究的代表性突破，介绍三个具有代表性的基础模型——Nicheformer、Squidiff和RegVelo，探索AI如何构建连接数据、机制与预测的新型研究范式。

- [腾讯发表Cell论文：用AI打通基因与药物筛选壁垒，加速AI虚拟细胞实现](https://mp.weixin.qq.com/s/TULPmzPhKGo3fPV5W4MV0g) — 2026 年 7 月 24 日，腾讯生命科学实验室（AI for Life Sciences Lab）姚建华研究员、杨帆研究员及中南大学计算机学院李敏教授作为共同通讯作者（李一鸣为论文第一作者），在国际顶尖学术期刊 Cell 上发表了题为：UniPert-G2CP bridges genetic and chemical screens from molecular representation to phenotype modeling 的研究论文。该研究构建了一个名为 UniPert-G2CP 的全新 AI 框架，通过整合多模态分子扰动因子（原因）表征，并实现从遗传到化学扰动表型（结果）的迁移学习，从而连接遗传筛选与化学筛选，从而更准确地预测扰动、发现作用机制，并实现高效的计算机辅助药物筛选。UniPert-G2CP 推动了通用生物学因果建模的发展，加速了人工智能虚拟细胞（AIVC）的实现，并拓展了 AI 驱动的精准医学的应用潜力。

- [17.5万美元奖金！2026虚拟细胞挑战赛开放报名，很火](https://mp.weixin.qq.com/s/zZYA3ztG5AKY_-tjGOApTQ) — 由Arc Institute主办，NVIDIA、10x Genomics和Ultima Genomics赞助的第二届Virtual Cell Challenge（虚拟细胞挑战赛）已经开放预注册，并将于2026年8月20日正式启动。

- [Squidiff: predicting cellular development and responses to perturbations using a diffusion model](https://www.nature.com/articles/s41592-025-02877-y)) — 单细胞测序彻底改变了我们对细胞异质性和环境刺激响应的理解。然而，绘制不同细胞类型在各种刺激下的转录组变化图谱并阐明潜在的疾病机制仍然是一项挑战。本文介绍了一种基于扩散模型的生成框架 Squidiff，该框架能够预测不同细胞类型在环境变化下的转录组变化。我们展示了 Squidiff 在细胞分化、基因扰动和药物反应预测方面的稳健性。通过持续去噪和语义特征整合，Squidiff 能够学习瞬态细胞状态，并预测不同时间和条件下的高分辨率转录组图谱。此外，我们将 Squidiff 应用于模拟血管类器官发育以及细胞对中子照射和生长因子的响应。我们的结果表明，Squidiff 能够对分子图谱和细胞状态转变进行计算机模拟筛选，从而促进快速假设生成，并为细胞命运决定的调控原理提供宝贵的见解。

## Cell Skeleton Modeling

- [Cell：虚拟“全细胞模型”，首次在电脑中模拟全细胞线粒体动态](https://mp.weixin.qq.com/s/rltQSBiSl8nLy19ec4UZqA) — 2026 年 6 月 30 日，加州大学圣地亚哥分校的研究人员在国际顶尖学术期刊 Cell 上发表了题为：Whole-cell particle-based digital twin simulations from 4D lattice light-sheet microscopy data 的研究论文。该研究把 4D 晶格光片显微镜（LLSM）拍到的活细胞动态和粒子反应-扩散模拟结合，构建了首个包含线粒体网络、微管网络、分子马达的全细胞数字孪生模型。不用反复做实验，只要在电脑里“拨动参数”，就能预测细胞在药物、应激压力下的变化，甚至发现了调控线粒体分布的隐藏规律。

## World Model

- [全球首个「虚拟细胞+世界模型」来了，David Baker领衔！](https://mp.weixin.qq.com/s/TJTdb3TGGN6cm8mI49-chw) — 这是全球首个能够跨完整生物层级模拟人类细胞的系统，既能模拟细胞自然状态，也可模拟细胞对药物及其他干预手段产生的应答，包含从DNA、RNA到蛋白质甚至完整细胞层面的多个生物层级。

- [GenBio AI：用世界模型把整个细胞装进模拟器](https://mp.weixin.qq.com/s/mj4XdAINEUPcOZXF_ZiKtA) — GenBio AI专注用AI模拟生物学，总裁兼首席科学家Eric Xing是机器学习领域知名学者。公司的核心使命是构建"AI驱动数字生物体"（AIDO）。

- [2,000万美元融资！虚拟组织世界模型](https://mp.weixin.qq.com/s/D0jtWkrG4ub9bXIbz6scDQ) — Polyphron是家研发人工人类生物学技术、致力于革新药物开发与疾病治疗的企业。该公司宣布完成2,000万美元种子轮融资，由Quiet Capital领投，Gradient、Haystack以及Compound参与投资。Polyphron训练前沿AI模型，实现活组织的制备与仿真，为AI驱动的生物学搭建验证载体。

## Clinical 

- [登上Science：国产医疗AI新突破！阿里×浙大合作开发专家级通用AI模型，一次识别146种病症](https://mp.weixin.qq.com/s/peWFy_I6Vs0KWVErC0yn-A) — 2026 年 9 月 18 日，浙江大学医学院附属第一医院梁廷波教授、章琦教授、肖文波教授联合阿里巴巴达摩院算法专家张灵、张建鹏等人，在国际顶尖学术期刊 Science 上发表了题为：An expert- level generalist AI for abdominal CT diagnosis 的研究论文。该研究开发了一款专家级通用医疗影像 AI 模型——RADAR，这是一种视觉-语言模型，在无需人工标注的情况下表现出色，即使面对训练过程中未曾见过的异常情况也能有效识别。论文显示，该模型用于腹部增强 CT 诊断，可一次性识别超过 146 种病症，其准确性首次达到影像科专家级水平，此外，RADAR 的辅助可使影像科专家的诊断敏感性提升了约 10%。

## Controversies

- [虚拟细胞为何成不了AlphaFold？](https://mp.weixin.qq.com/s/41kHsbyPFk5HaKtYuO-p-g) — 陈-扎克伯格计划CZI砸了5亿美元，Tahoe发了30亿参数的模型，Xaira推出了49亿参数的X-Cell。全球最顶级的风投和中东主权基金集体押注。模型参数从25万膨胀到49亿，预训练细胞从10万个涨到3.6亿个。然而，当聚光灯转向实验室，一个尴尬的事实逐渐浮出水面：在最核心的扰动预测任务上，这些耗资巨大的复杂AI模型，表现竟与一条简单的直线相差无几。

- [AI虚拟细胞被微软判“死刑”？砸钱堆数据白费了，效果还不如老古董算法！](https://mp.weixin.qq.com/s/6L-TReAllq2-1mixFpUi_A?scene=1)微软在《Nature Methods》上发表了一篇论文，直接给现在最火的“AI虚拟细胞”敲了一记警钟：你以为数据越多模型越强？在虚拟细胞这里，根本不成立。也就是说，行业从100万卷到上亿细胞数据的大战，可能全走错了方向。

- [Cell：生成式AI真正理解生命，还要解决的十五大挑战](https://mp.weixin.qq.com/s/uhj9xPCwTol0UyLSAEtZrA) — 2026 年 8 月 17 日，哥伦比亚大学、Biohub、西北大学、斯坦福大学、卡内基梅隆大学、耶鲁大学等机构的研究人员在国际顶尖学术期刊 Cell 上发表了题为：Fifteen challenges for generative AI applications to cell biology 的展望文章。

## Single-cell Analysis

- [The future of rapid and automated single-cell data analysis using reference mapping](https://www.cell.com/cell/fulltext/S0092-8674(24)00301-5) — 随着单细胞数据集数量的快速增长，将新数据映射到精心整理的参考图谱的工作流程为生物学界带来了巨大的希望。本文将探讨单细胞参考图谱映射算法面临的关键计算挑战和机遇。我们将讨论映射算法如何能够整合跨越疾病状态、分子模式、遗传扰动和不同物种的各种数据集，并最终取代繁琐的人工无监督聚类流程。

## Spatial Biology (Digest TME)

- [Paper title](https://doi.org/xxxxx) — 简单介绍。

## Others 

- [Nature | 基于空间生态类型的肿瘤微环境无创解析](https://mp.weixin.qq.com/s/wHZ3DRWr82xL9RsmzxosLg) — 本篇文献完整展现了一项从肿瘤空间生态发现到液体活检转化的研究。作者首先手机空间转录组平台的数据，利用Spatial EcoTyper识别具有稳定细胞状态及空间共定位特征的肿瘤生态系统；随后通过单细胞和bulk转录组数据验证其跨模态、跨队列的可重复性；最后进一步开发Liquid EcoTyper，将生态系统特征映射到血浆cfDNA甲基化信号中，实现对肿瘤微环境组成的无创推测。

- [肿瘤类器官登Nature！绘制迄今最大肿瘤类器官癌症基因依赖图谱，数据已公开！](https://mp.weixin.qq.com/s/8tlpkL3h3654Cof5-4qfPQ) — 2026年8月5日，英国威康桑格研究所M. J. Garnett团队在Nature在线发表题为“A tumour-derived organoid biobank maps cancer gene dependencies”的研究论文。研究团队建立了包含256个患者来源肿瘤类器官的可再生生物样本库，并对其中162个类器官开展全基因组CRISPR–Cas9筛选，将患者临床信息、全基因组测序、转录组、基因依赖性以及药物反应整合起来，构建了一张更加接近真实患者肿瘤的功能性癌症依赖图谱。这一开放且可公开获取的资源系统性地绘制迄今最大肿瘤类器官癌症基因依赖图谱，拓展了推动精准肿瘤学发展的模型多样性与机制理解。
