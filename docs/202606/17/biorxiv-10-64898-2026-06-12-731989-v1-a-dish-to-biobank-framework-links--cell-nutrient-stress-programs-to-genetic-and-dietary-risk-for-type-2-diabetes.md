---
title: A dish-to-biobank framework links β-cell nutrient-stress programs to genetic and dietary risk for Type 2 Diabetes
title_zh: 一种“从培养皿到生物库”框架将β细胞营养应激程序与2型糖尿病的遗传和饮食风险联系起来
authors: "Wang, X., Lee, H., Le, A., Turhan, B., Hu, N., Garcia, P. S., Cao, X., Liu, D., Ali, T. A., Zhang, N., Williams, B., Lareau, C. A., Wang, G., Huangfu, D., Dey, K. K."
date: 2026-06-16
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.12.731989v1.full.pdf"
tags: ["query:gwas"]
score: 8.0
evidence: 整合功能β细胞扰动与群体遗传学分析2型糖尿病
tldr: 2型糖尿病由遗传易感性与慢性代谢应激共同驱动，但两者是否汇聚于共享分子程序未知。本研究开发了从培养皿到生物库的框架，通过人干细胞来源胰岛的scRNA-seq发现葡萄糖和棕榈酸联合（糖脂毒性）诱导最强的β细胞转录反应，上调基因富集T2D遗传力、单基因糖尿病基因和罕见变异信号。CRISPR敲除PAX6/PDX1证实环境与遗传扰动汇聚于同一疾病相关状态。利用UK Biobank血浆蛋白质组定义可遗传应激特征，关联精细碳水化合物和饱和脂肪摄入及跨组织遗传调控，部分变异呈饮食依赖性效应。
source: biorxiv
selection_source: fresh_fetch
motivation: 遗传与代谢应激在T2D人群中是否通过共享分子程序致病尚不清楚，需要系统性框架实现从体外扰动到人群遗传学的桥接。
method: 对干细胞来源胰岛进行糖和棕榈酸因子处理，结合scRNA-seq、CRISPR敲除及UK Biobank血浆蛋白质组与遗传关联分析。
result: 糖脂毒性诱导的β细胞基因程序富集T2D遗传信号，血浆蛋白特征可遗传且与饮食摄入及遗传变异相互作用。
conclusion: 糖脂毒性是遗传锚定的β细胞功能障碍模型，该框架可推广至其他疾病的环境-遗传汇聚研究。
---

## 摘要
2型糖尿病（T2D）由遗传易感性和慢性代谢应激引起，但这些因素是否在人群水平上汇聚于共同的分子程序仍不清楚。在此，我们开发了一种“从培养皿到生物库”框架，通过循环血浆蛋白质组将受控的β细胞扰动与群体规模疾病遗传学联系起来，并将其应用于T2D。对人干细胞来源的胰岛进行因子化葡萄糖和棕榈酸暴露下的单细胞RNA测序，发现它们的组合（糖脂毒性）能引发最强的干细胞来源β细胞转录反应，且糖脂毒性上调基因在T2D遗传度、单基因糖尿病基因以及罕见变异负荷信号中独特富集。β细胞身份调控因子PAX6和PDX1的CRISPR敲除与该程序一致，确立了环境和遗传扰动在共同的疾病相关状态上的汇聚。随后，我们利用血浆蛋白质组作为这些实验定义的β细胞应激程序的可及群体水平读码，对45956名英国生物银行白人英国参与者进行评分。我们定义了与精制碳水化合物和饱和脂肪摄入相关的可遗传应激特征，这些特征经历了跨组织遗传调控，其中一部分变异显示出饮食依赖性效应。综上，这些发现确立了糖脂毒性作为β细胞功能障碍的遗传锚定模型，并提供了一种可推广的框架，用于将受控的细胞扰动与群体水平的人类疾病遗传学联系起来。

## Abstract
Type 2 diabetes (T2D) arises from genetic susceptibility and chronic metabolic stress, but whether these converge on shared molecular programs in human populations remains unclear. Here, we develop a dish-to-biobank framework linking controlled beta cell perturbation to population-scale disease genetics through the circulating plasma proteome, and apply it to T2D. scRNA-seq of human stem cell-derived islets under factorial glucose and palmitate exposure identifies their combination (glucolipotoxicity) as the condition eliciting the strongest SC-beta cell transcriptional response, with glucolipotoxicity-upregulated genes uniquely enriched for T2D heritability, monogenic diabetes genes, and rare-variant burden signals. CRISPR knockout of beta cell identity regulators PAX6 and PDX1 aligns with this program, establishing convergence of environmental and genetic perturbations on a shared disease-relevant state. We then used the plasma proteome as an accessible population-scale readout of these experimentally defined beta cell stress programs, scoring 45,956 UK Biobank White British participants. We define heritable stress signatures that associate with refined carbohydrate and saturated fat intake, and undergo trans-tissue genetic regulation, with a subset of variants showing diet-dependent effects. Together, these findings establish glucolipotoxicity as a genetically anchored model of beta cell dysfunction and provide a generalizable framework for linking controlled cellular perturbations to human disease genetics at population scale.

---

## 论文详细总结（自动生成）

# 论文总结：一种“从培养皿到生物库”框架将β细胞营养应激程序与2型糖尿病的遗传和饮食风险联系起来

## 1. 论文的核心问题与整体含义
- **研究动机**：2型糖尿病（T2D）由遗传易感性与慢性代谢应激共同驱动，但两者是否在人群水平上汇聚于共同的分子程序尚不清楚。
- **核心问题**：能否通过可控的体外β细胞扰动，桥接到大规模人群遗传学和饮食风险，揭示环境-遗传协同致病机制？
- **整体含义**：开发了一种可推广的框架（dish-to-biobank），利用循环血浆蛋白质组作为中介，将细胞水平的应激程序与群体遗传学联系起来，并发现糖脂毒性（高葡萄糖+棕榈酸）是遗传锚定的β细胞功能障碍模型。

## 2. 论文提出的方法论
- **核心思想**：通过体外实验定义β细胞营养应激的转录程序，然后在大型生物库（UK Biobank）中用血浆蛋白质组作为可及的群体水平读码，评估该程序与遗传变异、饮食因素的关联。
- **关键技术细节**：
  - **体外扰动**：对人干细胞来源的胰岛进行因子化葡萄糖和棕榈酸暴露（单独或联合），通过单细胞RNA测序（scRNA-seq）量化β细胞转录反应。
  - **遗传验证**：对β细胞身份调控因子PAX6和PDX1进行CRISPR敲除，观察其与糖脂毒性程序的转录一致性。
  - **群体分析**：利用UK Biobank 45,956名白人英国参与者的血浆蛋白质组数据，建立与实验定义的β细胞应激程序对应的蛋白特征（stress signatures），并分析其遗传力、与精制碳水化合物和饱和脂肪摄入的关联、跨组织遗传调控以及变异-饮食相互作用。
- **算法流程（文字说明）**：① 体外因子化处理→scRNA-seq鉴定差异基因；② 计算T2D遗传度、单基因糖尿病基因、罕见变异信号的富集；③ 提取糖脂毒性上调基因对应的血浆蛋白，构建应激特征评分；④ 进行蛋白质组全关联研究（pQTL）、饮食交互分析，评估特征的可遗传性和饮食依赖性。

## 3. 实验设计
- **使用数据集**：
  - 体外：人干细胞来源的胰岛（SC-beta cells）在不同浓度葡萄糖和棕榈酸组合处理下的scRNA-seq数据。
  - 群体：UK Biobank（45,956名白人英国参与者）的血浆蛋白质组数据、基因组数据、饮食问卷数据。
  - 遗传参考：T2D GWAS汇总统计、单基因糖尿病基因集、罕见变异负荷信号数据库。
- **Benchmark**：未明确设置传统意义上的benchmark，但通过对比不同处理条件（单独葡萄糖、单独棕榈酸 vs 联合糖脂毒性）的转录反应强度，以及对照CRISPR敲除实验，验证了程序的特异性。
- **对比方法**：主要比较了不同营养应激条件下的基因集富集，以及糖脂毒性上调基因与T2D遗传度、单基因糖尿病基因、罕见变异信号的富集程度是否显著高于其他条件或随机背景。

## 4. 资源与算力
- **文中未明确说明**：未提及使用的GPU型号、数量、训练时长等算力信息。仅指出使用了scRNA-seq数据分析、CRISPR实验、大规模蛋白质组遗传分析，但未提供计算资源细节。

## 5. 实验数量与充分性
- **实验组数**：至少包含以下主要实验：
  - 因子化葡萄糖和棕榈酸处理（至少4种条件：对照、单独葡萄糖、单独棕榈酸、联合），每组可能含多个生物学重复。
  - CRISPR敲除PAX6和PDX1的scRNA-seq实验。
  - UK Biobank中45,956人的蛋白质组特征评分及遗传分析（包括pQTL、饮食相关性、交互效应等）。
- **充分性**：实验设计较为全面，从体外细胞扰动到体内群体验证形成闭环，且涵盖了遗传、环境、饮食多个维度。但缺乏独立复制队列（仅利用UK Biobank一个群体，且局限于白人），也未进行跨种族验证。客观性和公平性方面，实验流程清晰，但未提及盲法或随机化细节。

## 6. 论文的主要结论与发现
- ① 葡萄糖和棕榈酸的联合暴露（糖脂毒性）在人干细胞来源β细胞中诱导最强的转录反应，且该反应独特地富集T2D遗传度、单基因糖尿病基因和罕见变异负荷信号。
- ② 敲除β细胞身份因子PAX6/PDX1产生的转录变化与糖脂毒性程序高度一致，表明环境和遗传扰动汇聚于共同的疾病相关状态。
- ③ 基于血浆蛋白质组构建的β细胞应激特征在UK Biobank中表现出可遗传性，并与精制碳水化合物和饱和脂肪摄入相关。
- ④ 该特征受跨组织遗传调控（即与多个组织的pQTL关联），且部分遗传变异对特征的影响依赖于饮食摄入（饮食依赖性效应）。
- ⑤ 糖脂毒性是遗传锚定的β细胞功能障碍模型，该“从培养皿到生物库”框架可推广至其他疾病的环境-遗传汇聚研究。

## 7. 优点
- **方法创新**：首次将体外β细胞应激程序通过血浆蛋白质组桥接到大规模人群遗传学，实现了从分子机制到群体流行病学的端到端整合。
- **实验设计严谨**：采用因子化实验设计明确区分单独与联合应激效应，并用CRISPR基因编辑提供了因果性证据。
- **临床转化潜力**：定义的应激特征可用于预测个体对高碳水/高饱和脂肪饮食的敏感性，为精准营养干预提供生物标记。
- **可推广性**：框架不局限于T2D，可应用于其他复杂疾病（如心血管病、脂肪肝）的环境-遗传交互研究。

## 8. 不足与局限
- **实验覆盖**：仅使用了一种干细胞来源的β细胞模型，未在其他胰岛模型（如原代人胰岛、其他分化方案）中复现。
- **群体限制**：UK Biobank分析限于白人英国人，缺乏种族多样性，限制了结论的普适性。
- **偏差风险**：血浆蛋白质组作为β细胞应激的替代读码，可能受其他组织（肝脏、脂肪、肌肉）贡献的污染，因果推断需谨慎。
- **饮食测量**：饮食数据来自食物频率问卷（FFQ），存在回忆偏倚和测量误差。
- **未进行纵向验证**：目前为横断面关联，无法确定应激特征与T2D发病的因果关系。
- **假阳性控制**：大规模蛋白质组遗传分析中多重检验校正虽可处理，但未报告具体阈值或稳健性检验。

（完）
