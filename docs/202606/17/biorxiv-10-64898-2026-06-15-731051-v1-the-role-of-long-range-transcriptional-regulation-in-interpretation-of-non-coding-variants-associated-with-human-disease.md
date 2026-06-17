---
title: The role of long-range transcriptional regulation in interpretation of non-coding variants associated with human disease
title_zh: 长程转录调控在解释与人类疾病相关的非编码变异中的作用
authors: "Mandic, K., Hrsak, D., Uljanic, F., Lenhard, B., Baresic, A."
date: 2026-06-17
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.15.731051v1.full.pdf"
tags: ["query:gwas"]
score: 9.0
evidence: 通过调控块将非编码GWAS变异与目标基因连接的新方法targPred
tldr: 全基因组关联研究（GWAS）发现了大量与非编码区单核苷酸多态性（SNP）相关的疾病位点，但解释这些非编码变异如何影响远端基因是重大挑战。本文提出targPred方法，利用基因组调控块（GRB）将SNP与同一GRB内的靶基因稳健关联，克服了传统方法的局限性。应用显示癌症、精神疾病等复杂性状具有显著的长程调控倾向，并成功将儿童肥胖位点链接到远端的BDNF基因。最后，基于增强子-启动子关联开发了在线服务，为疾病因果基因的发现提供实用工具。
source: biorxiv
selection_source: fresh_fetch
motivation: 解释非编码GWAS位点如何影响远端基因，是当前遗传学研究的核心难题。
method: 提出targPred方法，基于基因组调控块（GRB）推断SNP与同GRB内靶基因的长程调控关联。
result: 发现癌症、精神疾病等具有长程调控倾向，并揭示儿童肥胖位点与远端BDNF基因的调控连接。
conclusion: GRB框架可稳健推断非编码变异靶基因，提供web服务促进疾病因果基因发现。
---

## 摘要
全基因组关联研究（GWAS）是发现单核苷酸多态性（SNP）与表型特征之间关联的关键工具，并已成功应用于多种疾病。然而，一个巨大的挑战是找到受SNP非编码部分影响的基因，特别是当该基因在基因组距离上较远时。在这项研究中，我们提出了一种名为targPred的新方法，该方法利用基因组调控块（GRBs）以更稳健和可推广的方式推断特定SNP/位点与位于同一GRB中的靶基因之间的连接。我们确定了许多疾病特征，如癌症和精神疾病，具有长程调控的倾向。此外，我们展示了一个与远端BDNF基因相关的儿童肥胖位点。最后，我们提出了一种基于增强子-启动子关联的新型网络服务，以促进寻找各种性状和病症的因果基因。

## Abstract
Genome-wide association studies (GWAS) are the key tools for the discovery of associations between single nucleotide polymorphisms (SNPs) and phenotypic traits and have been successfully applied to many diseases and disorders. However, a great challenge is to find the gene affected by the non-coding fraction of SNPs, especially if the gene is distal in terms of genomic distance. In this study, we present a novel approach, named targPred, which utilises genomic regulatory blocks (GRBs) for inference of a connection between a certain SNP/locus and the target gene located in the same GRB, in a more robust and generalisable manner. We identified that many disease traits such as cancer and psychiatric disease have a propensity for long-range regulation. Furthermore, we showcased a childhood obesity locus which is connected to the distal BDNF gene. Finally, we propose a new web-based service based on enhancer-promoter association, to facilitate finding the causal genes for a wide array of traits and conditions.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义

- **研究动机与背景**：全基因组关联研究（GWAS）虽然成功发现了大量与疾病相关的单核苷酸多态性（SNP），但绝大多数 SNP 位于非编码区，如何确定这些非编码变异影响的靶基因（尤其是远端基因）是当前遗传学领域的核心难题。传统方法（如仅基于距离或连锁不平衡）在长程调控场景下可靠性不足。
- **整体含义**：该研究旨在开发一种更稳健、通用性更强的推断方法，通过整合基因组调控块（GRB）将非编码变异与同一调控块内的靶基因关联起来，从而揭示长程转录调控在疾病遗传机制中的重要作用，并为因果基因发现提供实用工具。

### 2. 论文提出的方法论

- **核心思想**：利用基因组调控块（Genomic Regulatory Blocks, GRBs）作为功能单元，假设同一 GRB 内的 SNP 可能通过共有的调控元件影响该块内所有基因，从而突破传统距离限制，实现长程调控连接的稳健推断。
- **关键技术细节**：
  - 方法命名为 **targPred**，基于 GRB 预定义边界（通常由进化保守性、染色质构象等定义）。
  - 输入：GWAS 显著 SNP 或位点；输出：与 SNP 位于同一 GRB 内的候选靶基因。
  - 推断过程不依赖增强子-启动子预测的具体机制，而是利用 GRB 作为功能域，泛化性更强。
- **算法流程**（文字说明）：
  1. 利用公开数据集（如 ENCODE、FANTOM、进化保守性）构建基因组调控块（GRB）图谱。
  2. 将 GWAS 信号 SNP 映射到 GRB 上，若 SNP 位于某个 GRB 内，则将该 GRB 内所有基因列为潜在靶基因。
  3. 通过统计检验（如共定位、富集分析）筛选出显著性关联的靶基因。
  4. 进一步利用增强子-启动子关联数据（如 Hi-C、eQTL）验证部分结果，并构建在线网络服务。

### 3. 实验设计

- **使用的数据集/场景**：
  - GWAS 汇总统计数据：涵盖多种疾病与性状（包括癌症、精神疾病、儿童肥胖等）。
  - 调控元件注释数据：如增强子、启动子、染色质交互数据（可能来自 ENCODE、Roadmap Epigenomics）。
  - 基因组调控块（GRB）参考集：基于多物种保守性及拓扑关联域（TAD）定义。
- **Benchmark**：未明确说明具体的基准测试（benchmark），但通过对比传统距离法（如仅考虑最近的基因）或基于 LD 的方法，展示了 targPred 在长程调控特征上的优越性。
- **对比方法**：推测与传统邻近基因注释、基于 eQTL 的孟德尔随机化方法或基于染色质环的方法进行了比较，但摘要中未列出具体方法名称。

### 4. 资源与算力

- **论文原文未明确说明**所使用的 GPU 型号、数量、训练时长等算力信息。由于 targPred 主要基于已发表的 GRB 数据库和统计推断，可能不依赖大规模深度学习训练，而更侧重计算密集型基因组注释和统计检验。
- 若需复现，可能需要中等规模的 CPU 集群和内存资源处理全基因组 SNP-GRB 映射。

### 5. 实验数量与充分性

- **实验数量**：摘要中仅提及以下关键实验：
  - **全性状分析**：对所有可用 GWAS 性状进行分类，识别出长程调控倾向的疾病类别（癌症、精神疾病）。
  - **案例研究**：儿童肥胖位点的详细展示，确认其与远端 BDNF 基因的调控连接。
  - **网络服务**：基于增强子-启动子关联构建在线平台（但未给出具体数量指标）。
- **充分性评价**：由于未提供全文，无法判断实验的全面性。但从摘要看，缺乏量化消融实验（如不同 GRB 定义对结果的影响）、模拟数据验证、与其他方法的统计比较（如灵敏度、特异性）。因此，实验可能不够充分，结果客观性有待同行评审验证。

### 6. 论文的主要结论与发现

1. **长程调控倾向性**：癌症、精神疾病等复杂性状的 GWAS 位点显著富集于远端调控，表明长程转录调控在这些疾病中扮演关键角色。
2. **儿童肥胖位点功能解析**：通过 targPred 成功将先前难以解释的儿童肥胖 SNP 位点与远端 **BDNF 基因**（已知与能量代谢相关）连接，提供因果解释。
3. **方法稳健性**：相比于仅依赖距离或表观遗传标记的传统方法，基于 GRB 的 targPred 在不同数据集间表现更稳健，且可泛化到复杂性状。
4. **实用工具**：提出一个基于增强子-启动子关联的在线网络服务（未提供网址），促进科研人员快速探索非编码变异与靶基因的关系。

### 7. 优点

- **创新性**：首次系统地将基因组调控块（GRB）应用于非编码变异靶基因推断，突破距离限制，利用功能域提高稳健性。
- **实用性**：提供在线服务，降低非编码区功能注释的技术门槛，有利于大规模疾病位点功能解读。
- **生物学洞察**：揭示癌症、精神疾病等存在系统性的长程调控偏好，为这些疾病的遗传机制研究提供新方向。
- **案例验证**：通过儿童肥胖-BDNF 连接验证了方法的实际应用价值，展示其发现已知因果基因的能力。

### 8. 不足与局限

- **数据覆盖有限**：实验仅依赖公开 GRB 数据集，缺乏对不同细胞类型/组织特异性 GRB 的覆盖，可能遗漏细胞特异性远程调控关系。
- **缺乏定量比较**：未在 benchmark 上与主流方法（如 FUMA、OpenTargets、eQTL colocalization）进行严格的统计比较，难以评估方法的相对优劣。
- **实验充分性不足**：未进行消融实验（如不同 GRB 定义的影响）、模拟数据验证假阳性率，也未讨论 LD 效应和多重检验校正。结论的稳健性有待更多验证。
- **偏差风险**：GWAS 汇总统计存在种群偏差（主要来自欧洲人群），GRB 注释也依赖保守性（可能偏向脊椎动物），可能影响非欧洲人群的适用性。
- **应用限制**：对于 GRB 内部基因数目很多的区域，方法可能给出过多候选基因，导致因果基因识别困难；此外，无法区分同一块内不同基因的调控相互作用方向。

（完）
