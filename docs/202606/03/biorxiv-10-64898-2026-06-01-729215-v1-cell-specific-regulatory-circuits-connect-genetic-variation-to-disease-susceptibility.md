---
title: Cell-specific regulatory circuits connect genetic variation to disease susceptibility
title_zh: 细胞特异性调控回路连接遗传变异与疾病易感性
authors: "Oelen, R., Korshevniuk, M., Niewold, J., Kaptijn, D., van der Werff, M., Bonder, M. J., sc-eQTLGen Consortium,, Franke, L. H., van der Wijst, M. G. P."
date: 2026-06-03
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.01.729215v1.full.pdf"
tags: ["query:gwas"]
score: 8.0
evidence: 单细胞多组学整合GWAS变异解释
tldr: "全基因组关联研究已确定数千个与免疫疾病相关变异，但多数位于非编码区，限制机制解读。本研究从264个体的563100个外周血单核细胞（未刺激或白色念珠菌刺激）产生单细胞多组学数据，在六种免疫细胞中定位1,571个eGenes和28,862个caPeaks，其中41%和11%显示刺激依赖性。通过重叠QTL和SCENIC+网络分析，识别1,861个双作用QTL（对疾病富集增强1.9倍）和62,932个调控三联体（1.7%受遗传控制）。该网络方法为精准解读遗传变异如何通过细胞特异性调控回路影响疾病易感性提供了框架。"
source: biorxiv
selection_source: fresh_fetch
motivation: 为解读免疫疾病相关非编码遗传变异的功能，需在特定细胞类型中整合转录组和染色质可及性数据，绘制调控QTL并解析其调控网络。
method: 使用单细胞多组学数据，在264个体的6种免疫细胞中定位eQTL和caQTL，并通过重叠QTL和SCENIC+识别双作用QTL和调控三联体。
result: "获得1,571个eGenes和28,862个caPeaks，41%和11%具有刺激依赖性；1,861个双作用QTL对疾病富集度增强1.9倍；62,932个调控三联体中1.7%受遗传控制。"
conclusion: 揭示遗传变异通过细胞特异性调控回路影响疾病易感性的机制，为治疗靶点优先排序提供新方法。
---

## 摘要
全基因组关联研究已鉴定出数千个与免疫相关疾病相关的变异，但大多数位于非编码区域，使得机制解释复杂化。调控定量性状位点（QTLs），如表达QTLs（eQTLs）和染色质可及性QTLs（caQTLs），为优先排序和解释这些疾病相关遗传变异提供了强大框架。当联合分析时，它们能更深入地揭示疾病背后的调控结构。我们从264名个体收集的563,100个匹配的外周血单核细胞中生成了同细胞、单细胞多组学数据，整合了转录组和染色质可及性信息，这些细胞在未刺激或经白色念珠菌（CA）刺激24小时后采集。在六种主要免疫细胞类型中，我们定位了顺式eQTL和-caQTL，鉴定了1,571个eGene和28,862个caPeak，其中41%和11%显示出刺激依赖性效应。最后，为了剖析这些QTL效应背后的调控机制，我们应用了两种互补策略：1. 将caQTL与eQTL重叠；2. 应用SCENIC+识别包含转录因子、其可能结合的染色质区域及由此可能调控的候选靶基因的调控三元组。通过第一种方法，我们鉴定了1,861个双重作用QTLs。这些双重QTLs对免疫相关疾病关联的富集程度是单一模态QTLs的1.9倍，突显了它们在疾病解释中的相关性。通过第二种方法，我们发现了62,932个调控三元组，其中1.7%受遗传控制。随后利用SCENIC+衍生的TF活性测量，我们可以研究遗传变异如何重新连接TF对基因表达的调控，最终塑造个体间疾病风险的差异。总之，我们的基于网络的方法为疾病中受扰乱的细胞背景和基因程序提供了新见解，为优先排序治疗靶点和制定疾病预防策略奠定了基础。

## Abstract
Genome-wide association studies have identified thousands of variants associated with immune-related diseases, yet most lie in non-coding regions, complicating mechanistic interpretation. Regulatory quantitative trait loci (QTLs), such as expression QTLs (eQTLs) and chromatin accessibility QTLs (caQTLs), offer a powerful framework for prioritization and interpretation of these disease-associated genetic variants. When analyzed together, they offer deeper insights into the regulatory architecture underlying disease. We generated same-cell, single-cell multi-omics data, integrating transcriptomic and chromatin accessibility information, from 563,100 matched peripheral blood mononuclear cells collected from 264 individuals, either unstimulated or stimulated for 24h with C. albicans (CA). Across six major immune cell types, we mapped both cis-eQTLs and -caQTLs, identifying 1,571 eGenes and 28,862 caPeaks, with 41% and 11% showing a stimulation-dependent effect. Finally, to dissect the regulatory mechanisms underlying these QTL effects, we applied two complementary strategies: 1. overlapping caQTLs with eQTLs; 2. applying SCENIC+ to identify regulatory triplets containing a transcription factor, the chromatin region it may bind to and the candidate target genes it thereby may regulate. With the first approach, we identified 1,861 dual-acting QTLs. These dual-QTLs showed 1.9-fold stronger enrichment for immune-related disease associations than single-modality QTLs, highlighting their relevance for disease interpretation. With the second approach, we found 62,932 regulatory triplets, of which 1.7% were under genetic control. By then leveraging the SCENIC+-derived TF activity measurements we could study how genetic variants can rewire TF control of gene expression, ultimately shaping inter-individual variation in disease risk. Together, our network-based approach offers new insights into the cellular contexts and gene programs perturbed in disease, providing a foundation for prioritizing therapeutic targets and informing strategies for disease prevention.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）
- **核心问题**：全基因组关联研究（GWAS）已鉴定出数千个与免疫疾病相关的遗传变异，但超过95%位于非编码区，难以直接解释其功能机制。传统的表达QTL（eQTL）仅能解释40-50%的GWAS位点，需要整合更多分子层（如染色质可及性）并考虑细胞类型和刺激环境特异性，才能更全面地理解遗传变异如何影响疾病易感性。
- **研究背景**：此前大规模QTL研究多基于bulk组织或单一分子层，忽略了细胞异质性和调控上下文。单细胞多组学技术（同时测量同一细胞的转录组和染色质可及性）为在细胞类型分辨率下解析调控机制提供了新可能。本研究旨在通过大规模单细胞多组学数据，结合调控网络推断，系统揭示遗传变异通过细胞特异性调控回路影响免疫疾病风险的机制。

## 2. 论文提出的方法论：核心思想、关键技术细节
- **核心思想**：联合分析同一细胞的基因表达和染色质可及性数据，在多种免疫细胞类型和刺激条件下定位eQTL和caQTL，并通过两种互补策略（1）重叠caQTL与eQTL识别“双重QTL”；（2）利用SCENIC+推断转录因子（TF）-顺式调控元件（CRE）-靶基因的三联体（eRegulons），进而研究遗传变异如何重连TF对基因表达的调控。
- **关键技术细节**：
  - **数据生成**：使用10x Genomics Chromium Next GEM单细胞多组学ATAC+基因表达试剂盒，对264名个体的PBMC进行同细胞多组学分析，包括未刺激和白色念珠菌（24h CA）刺激条件。共获得563,100个高质量细胞。
  - **QTL定位**：采用LIMIX-QTL混合效应模型，分别对基因表达和染色质可及性进行cis-QTL映射，并利用SuSiE进行精细定位。交互QTL分析以刺激状态为交互项。
  - **双重QTL**：将同一细胞类型中同时影响染色质可及性和基因表达的遗传变异定义为双重QTL，共1,861个。
  - **调控网络推断**：使用SCENIC+基于单细胞数据推断TF-CRE-靶基因的eRegulons，共识别109,787个调控三联体。进一步将QTL结果与eRegulons重叠，鉴定受遗传控制的调控三元组。
  - **TF活性-基因表达交互QTL（TFa-i-eQTL）**：利用SCENIC+计算的TF活性（AUCell得分），在线性混合模型中测试遗传变异与TF活性对靶基因表达的交互作用，以识别遗传变异如何改变TF调控效力。共发现3,857个显著TFa-i-eQTL效应。

## 3. 实验设计：数据集、基准、对比方法
- **数据集**：
  - **主要数据集**：来自荷兰北部人群的264名健康捐献者（25-85岁，59%女性）的PBMC，含未刺激（128人）和24h CA刺激（187人）样本。每个样本池8人，使用10x多组学平台捕获约2,500个细胞/人。
  - **外部验证集**：
    - eQTL：OneK1K（982人PBMC sc-eQTL研究）和eQTLGen（31,682人bulk全血）。
    - caQTL：来自1000 Genomes Project的91人的LCL B细胞bulk ATAC-seq数据（Kumasaka et al.）。
  - **参考数据库**：JASPAR/HOCOMOCO TF结合基序数据库、STRING蛋白互作数据库、K562 Hi-C数据、ENCODE调控元件注释等。
- **基准（Benchmark）**：
  - eQTL验证：与OneK1K和eQTLGen的效应方向一致性和rb相关性比较。
  - caQTL验证：与LCL B细胞caQTL数据集比较，注重B细胞匹配。
  - 调控三联体验证：与STRING数据库、K562 Hi-C互作数据、REUNION方法的预测结果比较。
- **对比方法**：
  - 对于GRN推断，主要使用SCENIC+，并与REUNION方法进行重叠比较。
  - 在TFa-i-eQTL分析中，还与CRE-i-eQTL（使用CRE可及性）和TFe-i-eQTL（使用TF表达）结果对比，显示TF活性指标捕获了更多信息。

## 4. 资源与算力
- **文中未明确提及**具体的计算资源（如GPU型号、数量、训练时长等）。仅提到测序在BGI（香港）的MGI2000测序仪上进行，100bp双端测序。数据分析使用了集群（Genomics Coordination Center，格罗宁根大学信息技术中心），但未详细说明计算资源消耗。

## 5. 实验数量与充分性
- **实验数量**：
  - 主分析：在6种主要免疫细胞类型（B、CD4+ T、CD8+ T、NK、DC、单核细胞）中分别进行了4类QTL映射（eQTL、caQTL、刺激交互eQTL、刺激交互caQTL），共产生1,571个eGene、28,862个caPeak、1,861个双重QTL，以及62,932个调控三联体。
  - 验证实验：与OneK1K、eQTLGen、LCL caQTL进行跨数据集一致性比较；与STRING、Hi-C、REUNION进行调控网络交叉验证。
  - 消融/敏感性分析：对TFa-i-eQTL进行循环性检验（排除靶基因后重新计算TF活性），2%被排除；对双重QTL进行LD修剪和疾病富集分析（Fisher精确检验）。
- **充分性与公平性**：
  - **充分性**：涵盖了多种细胞类型、两种刺激状态，使用了多层面QTL和GRN方法，外部队列验证结果表明结果稳健。刺激交互分析显示41% eGene和11% caPeak具有上下文依赖性，符合生物学预期。
  - **客观公平**：与外部数据的对比方法一致（rb相关性、方向一致性），控制了统计检验（Permutation、Benjamini-Hochberg FDR）。但部分对比（如SCENIC+ vs REUNION）仅在重叠部分评估一致性，未对整体性能进行完整benchmark。

## 6. 论文的主要结论与发现
- **发现1**：eQTL和caQTL具有明显的细胞类型特异性，但效应大小在同谱系细胞间高度共享（rb达0.61-0.95），大部分特异性可能源于统计检验力差异。
- **发现2**：刺激依赖性QTL（stam-i-eQTL/caQTL）更倾向于位于远端增强子区域，而基线QTL主要位于近端调控区域，支持上下文特异性调控主要由增强子介导。
- **发现3**：双重QTL（同时影响染色质和表达）数量为1,861个，其中78%为正向关联（开放增加→表达增加）。与单模态QTL相比，双重QTL对免疫疾病GWAS信号的富集程度提高1.9倍，显著提升因果变异识别能力。
- **发现4**：通过SCENIC+识别的调控三联体中，1.7%受遗传控制；进一步利用TFa-i-eQTL分析，25.7%的遗传调控三联体可归因于TF活性与基因型的交互作用，说明遗传变异通过改变TF调控效力影响基因表达。
- **发现5**：以系统性红斑狼疮（SLE）和青少年特发性关节炎（JIA）为例，展示了如何通过此框架为已知GWAS位点提供细胞类型特异性的机制解释（如UHRF1BP1、BLK-FAM167A、ERAP2等位点），涉及染色质环、TF结合偏好改变等机制。

## 7. 优点
- **方法论亮点**：
  - 首创在单细胞分辨率下同时测量同一细胞的基因表达和染色质可及性，避免了bulk层面的平均效应和细胞类型特异性信号丢失。
  - 联合QTL与GRN推断，不仅鉴定影响分子表型的变异，还揭示其如何通过改变TF调控网络起作用，提供了更深层的机制视角。
  - 采用TF活性而非TF表达或CRE可及性作为调控活性度量，显著提升了检测遗传-调控交互的统计检验力（TFa-i-eQTL远多于CRE-i-eQTL和TFe-i-eQTL）。
  - 双重QTL疾病富集分析直接量化了多模态整合的增益价值，具有较强的实践指导意义。
- **实验设计亮点**：
  - 包含刺激条件（白色念珠菌），能够捕获上下文特异性调控，这对理解免疫应答过程中的遗传影响至关重要。
  - 使用外部多数据集验证（OneK1K、eQTLGen、LCL caQTL），确保了主要效应的可重复性。
  - 精细定位（SuSiE）和严格的统计控制（Permutation、FDR、循环性检验）提高了可信度。

## 8. 不足与局限
- **实验覆盖的局限性**：
  - 仅包含6种主要免疫细胞类型，未涉及稀有亚群（如γδ T细胞、浆细胞等），可能遗漏特定细胞类型的调控机制。
  - 仅测试了白色念珠菌刺激一种病原体，未能覆盖更广泛的免疫刺激条件。
  - 样本量（264人）相对有限，尤其对于DC等稀有细胞类型，统计检验力较低，可能遗漏许多真实QTL。
- **方法内在局限**：
  - SCENIC+依赖已知TF基序数据库（JASPAR/HOCOMOCO），仅覆盖约50%的TF，且无法检测不直接结合DNA的共调节因子。
  - SCENIC+未显式建模遗传变异，可能错过受遗传影响较大的调控三联体；作者建议未来工具应直接考虑基因型信息。
  - 双重QTL和调控三联体均为统计关联，缺乏大规模功能性验证（如CRISPR扰动、报告基因实验），仅在少数位点引用了前人实验证据（如BLK位点的CRISPR验证）。
- **偏差风险**：
  - 人群来源仅为荷兰北部欧洲白人背景，泛化至其他祖先人群需谨慎。
  - 细胞注释依赖参考数据集（10x Multiome PBMC v1.0），可能引入参考偏差。
  - 交互QTL分析中的效应估计可能受批次效应和伪重复影响，尽管混合模型部分校正。
- **应用限制**：
  - 结果主要作为假说生成和优先级排序的基础，不能直接用于因果推断；实验验证仍是必需步骤。

（完）
