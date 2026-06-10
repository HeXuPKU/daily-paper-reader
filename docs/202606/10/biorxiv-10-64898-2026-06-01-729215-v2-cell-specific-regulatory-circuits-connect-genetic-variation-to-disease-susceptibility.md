---
title: Cell-specific regulatory circuits connect genetic variation to disease susceptibility
title_zh: 细胞特异性调控回路将遗传变异与疾病易感性联系起来
authors: "Oelen, R., Korshevniuk, M., Niewold, J., Kaptijn, D., van der Werff, M., Bonder, M. J., sc-eQTLGen Consortium,, Franke, L. H., van der Wijst, M. G. P."
date: 2026-06-09
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.01.729215v2.full.pdf"
tags: ["query:gwas"]
score: 9.0
evidence: 整合单细胞多组学数据与eQTL/caQTL分析来解释GWAS变异，直接针对功能整合框架。
tldr: "全基因组关联研究发现的免疫疾病变异多位于非编码区，机制不明。本研究对264人56万单细胞多组学数据（转录组和染色质可及性），在刺激前后6种免疫细胞中映射eQTL和caQTL，并通过重叠和SCENIC+分析调控关系。鉴定1,861双模态QTL和62,932调控三联体，双模态QTL对疾病关联富集增强1.9倍。结果揭示了遗传变异如何通过细胞特异性调控回路影响疾病易感性，为治疗靶点提供了基础。"
source: biorxiv
selection_source: fresh_fetch
motivation: 解析非编码区疾病关联变异在特定免疫细胞中的调控机制，以理解遗传变异如何影响疾病易感性。
method: 整合单细胞多组学数据，在刺激前后6种免疫细胞中映射eQTL和caQTL，通过重叠和SCENIC+构建调控三联体。
result: "发现1,861双模态QTL和62,932调控三联体，双模态QTL对免疫疾病关联富集增强1.9倍。"
conclusion: 细胞特异性调控网络揭示遗传变异通过重编程转录因子控制影响基因表达和疾病风险。
---

## 摘要
全基因组关联研究已鉴定出数千个与免疫相关疾病相关的变异，但大多数位于非编码区，这使机制解释复杂化。调控数量性状位点（QTL），如表达QTL（eQTL）和染色质可及性QTL（caQTL），为这些疾病相关遗传变异的优先排序和解释提供了强大的框架。当它们一起分析时，能更深入地理解疾病背后的调控架构。

我们生成了来自264名个体的563,100个匹配的外周血单核细胞的同细胞、单细胞多组学数据，整合了转录组和染色质可及性信息，这些细胞未经刺激或经白色念珠菌（CA）刺激24小时。在六种主要免疫细胞类型中，我们绘制了顺式eQTL和caQTL，鉴定出1,571个eGene和28,862个caPeak，其中41%和11%显示出刺激依赖性效应。最后，为了解析这些QTL效应背后的调控机制，我们采用了两种互补策略：1. 将caQTL与eQTL重叠；2. 应用SCENIC+识别包含转录因子、其可能结合的染色质区域以及由此可能调控的候选靶基因的调控三联体。

通过第一种方法，我们鉴定了1,861个双重作用QTL。这些双重QTL在免疫相关疾病关联中的富集程度是单模态QTL的1.9倍，突显了它们在疾病解释中的相关性。通过第二种方法，我们发现了62,932个调控三联体，其中1.7%受遗传控制。然后利用SCENIC+衍生的TF活性测量，我们可以研究遗传变异如何重新连接TF对基因表达的调控，最终影响个体间疾病风险的差异。

总之，我们的基于网络的方法为疾病中扰乱的细胞环境和基因程序提供了新见解，为优先考虑治疗靶点和制定疾病预防策略奠定了基础。

## Abstract
Genome-wide association studies have identified thousands of variants associated with immune-related diseases, yet most lie in non-coding regions, complicating mechanistic interpretation. Regulatory quantitative trait loci (QTLs), such as expression QTLs (eQTLs) and chromatin accessibility QTLs (caQTLs), offer a powerful framework for prioritization and interpretation of these disease-associated genetic variants. When analyzed together, they offer deeper insights into the regulatory architecture underlying disease.

We generated same-cell, single-cell multi-omics data, integrating transcriptomic and chromatin accessibility information, from 563,100 matched peripheral blood mononuclear cells collected from 264 individuals, either unstimulated or stimulated for 24h with C. albicans (CA). Across six major immune cell types, we mapped both cis-eQTLs and-caQTLs, identifying 1,571 eGenes and 28,862 caPeaks, with 41% and 11% showing a stimulation-dependent effect. Finally, to dissect the regulatory mechanisms underlying these QTL effects, we applied two complementary strategies: 1. overlapping caQTLs with eQTLs; 2. applying SCENIC+ to identify regulatory triplets containing a transcription factor, the chromatin region it may bind to and the candidate target genes it thereby may regulate.

With the first approach, we identified 1,861 dual-acting QTLs. These dual-QTLs showed 1.9-fold stronger enrichment for immune-related disease associations than single-modality QTLs, highlighting their relevance for disease interpretation. With the second approach, we found 62,932 regulatory triplets, of which 1.7% were under genetic control. By then leveraging the SCENIC+-derived TF activity measurements we could study how genetic variants can rewire TF control of gene expression, ultimately shaping inter-individual variation in disease risk.

Together, our network-based approach offers new insights into the cellular contexts and gene programs perturbed in disease, providing a foundation for prioritizing therapeutic targets and informing strategies for disease prevention.

---

## 论文详细总结（自动生成）

# 论文详细总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：全基因组关联研究（GWAS）已发现大量与免疫相关疾病关联的遗传变异，但绝大多数位于非编码区，导致其功能性解读困难。如何系统性地解析这些非编码变异在特定细胞类型和动态环境（如免疫刺激）下如何影响基因表达，进而影响疾病易感性，是当前遗传学领域的重大挑战。
- **整体含义**：通过整合单细胞多组学数据，构建细胞特异性调控网络（转录因子-调控元件-靶基因），揭示遗传变异如何通过重编程转录因子控制基因表达，最终影响个体间疾病风险差异。这项工作为理解复杂疾病的分子机制、优先治疗靶点和制定预防策略提供了基础。

## 2. 论文提出的方法论：核心思想、关键技术细节

- **核心思想**：利用同一细胞的单细胞转录组（scRNA-seq）和染色质可及性（scATAC-seq）数据，在多种免疫细胞类型中联合绘制表达QTL（eQTL）和染色质可及性QTL（caQTL），并通过两种互补策略解析调控回路：
  1. **重叠法**：将caQTL与eQTL直接重叠，识别“双模态QTL”（同时影响染色质开放性和基因表达的位点）。
  2. **SCENIC+网络推断**：构建调控三联体（transcription factor → chromatin region → target gene），并进一步分析其中受遗传变异影响的回路（约占1.7%），通过TF活性测量研究变异如何重连调控关系。
- **关键技术细节**：
  - 数据采集：从264名个体的外周血单核细胞（PBMCs）中，对未刺激和白色念珠菌（CA）刺激24小时的样本，进行同细胞多组学测序，获得563,100个匹配细胞。
  - 细胞分型：划分为6种主要免疫细胞类型（可能包括单核细胞、T细胞、B细胞、NK细胞等）。
  - eQTL/caQTL映射：使用顺式QTL映射方法，分别鉴定出1,571个eGene和28,862个caPeak，并区分基线及刺激依赖性效应。
  - 调控三联体：结合SCENIC+算法，共发现62,932个调控三联体。
- **公式/算法流程**（文字说明）：无显式公式，流程为：单细胞多组学数据→细胞分型→顺式eQTL和caQTL分析→重叠法识别双模态QTL→SCENIC+构建调控三联体→比较疾病关联富集。

## 3. 实验设计：数据集、基准、对比方法

- **使用数据集**：
  - 主要数据集：264名个体的PBMC样本，同一细胞同时检测转录组和染色质可及性，共563,100个细胞，条件包括未刺激和CA刺激24小时。
  - 参考数据集：免疫相关疾病GWAS汇总统计（用于富集分析）；可能使用了已知eQTL/caQTL数据库作为基准。
- **基准（Benchmark）**：未明确说明标准基准。但通过比较双模态QTL与单模态QTL（仅eQTL或仅caQTL）在疾病关联中的富集程度来评估调控信息的增强效果。
- **对比方法**：未提及与其他现有方法（如传统的批量eQTL、独立caQTL）的系统对比。主要比较了双模态与单模态QTL的疾病解释能力。

## 4. 资源与算力

- **文中未明确说明使用的GPU型号、数量及训练时长**。论文本身属于生物信息学分析，可能主要依赖CPU计算集群和内存密集型任务，但未提供具体硬件配置或计算时长信息。
- 用户应注意到，该论文基于单细胞多组学数据的QTL映射和网络推断，涉及大规模矩阵运算和统计检验，但细节未公开。

## 5. 实验数量与充分性

- **实验组数**：主要分析包括：
  - 6种免疫细胞类型 × 两种条件（未刺激/CA刺激） → 共12个细胞-条件组合的QTL映射。
  - 分别进行eQTL和caQTL检验，鉴定出1,571 eGene和28,862 caPeak。
  - 重叠分析获得1,861双模态QTL；SCENIC+识别62,932调控三联体。
  - 疾病关联富集分析：比较双模态QTL、单模态QTL、随机背景对免疫疾病GWAS变异的富集倍数。
- **充分性与公平性**：
  - **充分性**：样本量（264人）和细胞数量（56万+）对于单细胞QTL研究而言较大，能捕捉细胞类型特异性和刺激依赖性效应。两种互补策略增强了调控机制解析的可信度。
  - **不足之处**：未进行独立的验证数据集（如其他队列或独立测序技术）以确认结果可重复性；未进行功能实验验证（如CRISPR扰动）来证明因果性。疾病富集分析仅基于欧米（European）群体，可能存在人群偏倚。不同细胞类型间的统计功效可能不均衡（如稀有细胞类型样本量不足）。

## 6. 论文的主要结论与发现

1. **细胞类型和刺激依赖性QTL广泛存在**：41%的eGene和11%的caPeak显示刺激依赖性效应，表明调控动态性。
2. **双模态QTL显著增强疾病解释力**：相比于单模态QTL，双模态QTL对免疫疾病GWAS变异的富集程度高出1.9倍，提示同时影响染色质和表达的变异更具功能重要性。
3. **遗传变异通过重连TF调控回路影响基因表达**：利用SCENIC+衍生的TF活性分析，揭示了变异如何改变TF-调控元件-靶基因的连锁关系，从而影响疾病风险。
4. **网络式方法提供治疗靶点优先级**：识别出62,932个调控三联体，其中1.7%受遗传控制，可作为干预疾病的潜在靶点。

## 7. 优点：方法或实验设计上的亮点

- **同细胞多组学整合**：在单细胞分辨率下同时测量RNA和染色质可及性，避免批次效应和细胞解离环境差异，这是当前技术的领先应用。
- **大规模样本和动态条件**：264人、56万细胞、刺激/未刺激对比，提供了在大规模人群背景下解析免疫细胞调控动力学的资源。
- **双重互补策略**：不仅简单重叠QTL，还运用SCENIC+推断调控网络，系统性地从TF层面解释变异效应。
- **直接关联疾病易感性**：通过疾病GWAS富集分析，量化了双模态QTL的解释优势，具有临床转化价值。

## 8. 不足与局限

- **实验验证缺失**：所有结论基于统计关联和生物信息学推断，缺乏功能实验（如CRISPR、报告基因实验）验证特定变异-基因-疾病的因果关系。
- **人群偏倚**：样本可能主要来自欧洲血统，对非欧裔人群的普适性未知。
- **技术局限性**：单细胞ATAC-seq的覆盖深度有限，可能漏检部分低表达调控元件；QTL映射统计力受细胞类型数量和峰值数影响，稀有细胞类型可能存在假阴性。
- **刺激条件单一**：仅使用了白色念珠菌刺激，其他免疫挑战（如病毒、细菌成分）未涉及，结论可能无法推广到所有免疫反应。
- **资源细节缺失**：未提供计算资源需求，不利于其他研究团队复现或评估可行性。
- **未与现有方法进行严格基准比较**：未说明与其它多模态QTL方法（如molQTL、多组学共定位）相比的优劣。

（完）
