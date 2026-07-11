---
title: Kernelized approach enables explainable gene prioritizations for complex traits
title_zh: 核化方法实现复杂性状的可解释基因优先级排序
authors: "Tan, T., Samee, M. A. H."
date: 2026-07-10
pdf: "https://www.biorxiv.org/content/10.64898/2026.07.08.737338v1.full.pdf"
tags: ["query:gwas"]
score: 9.0
evidence: 可解释的GWAS位点基因优先级排序
tldr: GWAS难以确定效应基因，现有优先级方法如PoPS缺乏解释性。K-PoPS通过核化分解每个预测为训练基因的贡献，提供基因中心解释。在38个UK Biobank性状中，其全特征OLS实现改进了最近基因富集，并由锚点评分支持更可靠的预测。K-PoPS为解释GWAS效应基因提名提供了后验框架。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-08-737338-v1/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1742, \"height\": 2135, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-08-737338-v1/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1663, \"height\": 1913, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-08-737338-v1/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1836, \"height\": 1516, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-08-737338-v1/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1820, \"height\": 839, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-08-737338-v1/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1840, \"height\": 773, \"label\": \"Figure\"}]"
motivation: 现有类似PoPS的方法优先效应基因但缺乏解释性，无法说明为何优先或提名是否合理。
method: K-PoPS核化重述PoPS，将每个预测分解为训练基因的贡献，并计算锚点评分量化查询基因集的支持。
result: 在38个性状中，全特征OLS实现改进了26个性状的最近基因富集；在25个性状中，锚点评分支持预测的富集更高。
conclusion: K-PoPS提供了一个后验框架，用于检查和解释GWAS效应基因提名，识别多个合理效应基因。
---

## 摘要
全基因组关联研究（GWAS）已识别出大量变异-性状关联；然而，将效应基因分配给GWAS位点仍具挑战性。基于相似性的机器学习方法，如PoPS，通过性状相关基因间的共享功能图谱对效应基因进行优先级排序。这些模型为每个基因分配优先级评分，并在GWAS位点内提名单个效应基因。然而，这些评分对于为何某个基因被优先考虑或该提名是否具有生物学合理性所提供的见解有限。为弥补这一不足，我们引入了核化多基因优先级评分（K-PoPS），这是PoPS的核化重构版本，通过将每个预测分解为来自训练基因的贡献来实现以基因为中心的解释。对于每个优先排序的基因，K-PoPS报告主要贡献基因以及一个锚定评分，该评分量化来自用户定义的性状相关基因集的支持。在38个Pan-UK Biobank性状中，K-PoPS底层使用全特征OLS实现，相比默认PoPS，在37个可评估性状中的26个中改善了最近基因富集。在具有人工锚定集的25个性状中，由锚定评分支持的预测比未支持的预测在最近基因代理方面更富集。当应用于血液载脂蛋白B水平时，K-PoPS提名了SCARB1而非UBC基因，并进一步提供了支持该预测的令人信服的解释。利用解释证据，K-PoPS在一个扩张型心肌病位点内识别了多个合理的效应基因，这与简约性假设相反。总之，K-PoPS提供了一个事后框架，用于检查和解释GWAS效应基因提名。

## Abstract
Genome-wide association studies (GWAS) have identified numerous variant-trait associations; yet, assigning effector genes to GWAS loci remains challenging. Similarity-based machine-learning methods, such as PoPS, prioritize effector genes from shared functional profiles among trait-relevant genes. These models assign a prioritization score for each gene and nominate a single effector gene within a GWAS locus. However, the scores provide limited insight into why a gene was prioritized or whether the nomination is biologically plausible. To address this gap, we introduce Kernelized Polygenic Priority Score, K-PoPS, a kernelized reformulation of PoPS that enables gene-centric explanations by decomposing each prediction into contributions from training genes. For each prioritized gene, K-PoPS reports top contributor genes and an anchor score that quantifies support from a user-defined set of trait-relevant genes. Across 38 Pan-UK Biobank traits, the full-feature OLS implementation underlying K-PoPS improved closest-gene enrichment relative to default PoPS for 26 of 37 evaluable traits. Across 25 traits with curated anchor sets, predictions supported by anchor scores were more enriched for closest-gene proxies than unsupported predictions. When applying to blood level apolipoprotein B, K-PoPS nominated SCARB1 over UBC gene, and further provided convincing explanations that support this prediction. Using explanation evidence, K-PoPS identified multiple plausible effector genes within a dilated cardiomyopathy locus, contrary to the parsimonious assumption. In summary, K-PoPS provides a post hoc framework for examining and interpreting GWAS effector-gene nominations.

---

## 论文详细总结（自动生成）

# 论文中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：全基因组关联研究（GWAS）已鉴定出大量变异与性状之间的关联，但如何准确地将效应基因分配给GWAS位点仍然是一个重大挑战。
- **现有方法不足**：基于相似性的机器学习方法（如PoPS）通过性状相关基因间的共享功能图谱对效应基因进行优先级排序，为每个基因赋予评分并提名单一效应基因。然而，这些评分未能解释**为何某个基因被优先考虑**，也无法判断提名是否具有**生物学合理性**，即缺乏可解释性。
- **研究目标**：提出一个后验（post hoc）解释框架，使得GWAS效应基因提名不仅可量化，更能提供以基因为中心的详细解释，从而增进对提名合理性的理解。

## 2. 论文提出的方法论：核心思想、关键技术细节

- **方法名称**：K-PoPS（Kernelized Polygenic Priority Score）
- **核心思想**：将PoPS方法进行**核化重构**，将每个优先基因的预测评分分解为**来自训练基因的贡献**，从而实现以基因为中心的解释。
- **关键技术细节**：
  - 对于每个被优先排序的基因，K-PoPS报告：
    - **主要贡献基因**：对预测贡献最大的训练基因。
    - **锚点评分（anchor score）**：量化来自用户定义的性状相关基因集（锚定集）对该预测的支持程度。
  - 底层实现采用**全特征普通最小二乘法（full-feature OLS）**，替代默认PoPS中的其他特征选择/正则化策略。
- **输出形式**：不仅给出每个基因的优先级评分，还提供贡献分解和锚定支持度，使得预测具有可追溯的解释。

## 3. 实验设计：数据集、基准、对比方法

- **数据集**：
  - **主要数据集**：Pan-UK Biobank中的**38个性状**。
  - **人工锚定集**：针对其中25个性状构建了用户定义的性状相关基因集，用于评估锚点评分的有效性。
- **基准（Benchmark）**：
  - **最近基因富集（closest-gene enrichment）**：考察优先基因是否为距离GWAS信号最近的基因（最简代理），以衡量预测的合理性。
- **对比方法**：
  - 主要与**默认PoPS**进行对比，比较K-PoPS底层全特征OLS实现与PoPS在最近基因富集上的表现。
  - 在锚定分析中，比较**得到锚点评分支持的预测**与**未得到支持的预测**在最近基因代理上的富集程度。

## 4. 资源与算力

- **文中未明确说明**训练所使用的GPU型号、数量、训练时长等硬件资源或算力需求。仅在方法层面描述了计算框架，未提及具体算力开销。

## 5. 实验数量与充分性

- **实验数量**：
  - 在38个性状中，37个性状可用于比较，其中**26个**性状上K-PoPS的全特征OLS实现优于默认PoPS的最近基因富集。
  - 在25个具有人工锚定集的性状中，**锚点评分支持的预测**比未支持的预测在最近基因代理方面更富集。
  - 包含两项案例分析：血液载脂蛋白B水平（提名SCARB1而非UBC）、扩张型心肌病位点（识别多个合理效应基因）。
- **充分性评估**：
  - 实验覆盖了多种性状（38个），具有较好的广度；锚定分析验证了可解释机制的有效性。
  - 但**缺乏与其他主流基因优先级方法（如S-LDSC、DEPICT、FINEMAP等）的系统对比**，也**未进行消融实验**（如移除核化分解或锚定机制的影响）。因此实验设计在一定程度上是合理的，但全面性可进一步加强。

## 6. 论文的主要结论与发现

1. **性能提升**：在全特征OLS实现下，K-PoPS在多数性状上改善了最近基因富集，优于默认PoPS（26/37个可评估性状）。
2. **可解释性价值**：锚点评分能有效区分更可靠的预测，获得锚定支持的预测更倾向于接近GWAS信号最近的基因，说明解释性定量指标与生物学合理性相关。
3. **案例验证**：
   - 在血液载脂蛋白B中，K-PoPS正确提名了已知关键基因**SCARB1**（而非邻近的UBC），并提供了可解释的贡献证据。
   - 在扩张型心肌病位点，K-PoPS识别出多个合理效应基因，挑战了传统的单一效应基因假设。
4. **框架定位**：K-PoPS作为一个**后验解释框架**，可帮助研究者检查和解释GWAS效应基因提名，增强对机器学习预测结果的理解和信任。

## 7. 优点

- **突破性解释能力**：首次将核化分解机制引入GWAS基因优先级排序，使每个预测的贡献可回溯到特定训练基因，响应了“黑箱”批判。
- **锚点评分创新**：引入用户定义的性状相关基因集的支持度量，赋予了预测一个可量化的生物学可信度指标。
- **易于理解和应用**：方法逻辑清晰，直接基于PoPS重构，便于现有用户迁移使用；代码或实现应易获得（未在摘要中说明但可推测）。
- **生物学验证**：通过两个具体案例展示了方法在实际应用中如何纠正错误提名（UBC→SCARB1）并发现多基因位点，具有较强的说服力。

## 8. 不足与局限

- **锚定集构建的主观性**：锚点评分依赖于用户定义的性状相关基因集，若锚定集选择不当或有偏，可能影响解释质量。文中未讨论如何确保锚定集的最优或自动构建。
- **对比方法单一**：仅与默认PoPS比较，未纳入其他广泛使用的基因优先级工具（如FINEMAP、SMR、TWAS等），不足以全面评估方法的优越性。
- **缺少消融实验**：没有验证是否核化分解本身（而非底层OLS实现）带来了解释优势，也未测试不同核函数或分解策略的影响。
- **计算资源未说明**：未报告运行时间或内存需求，对于高通量分析来说，效率信息缺失。
- **样本与性状限制**：实验基于UK Biobank的38个性状，种族/人口结构较为单一，代表性受限；泛化到其他人群或更复杂性状仍有待验证。
- **仅做富集评估**：主要基准是最近基因代理，但“最近基因”本身并非金标准，可能存在遗漏真实效应基因的情况；需要更多功能验证（如CRISPR、eQTL共定位）来坚实支撑结论。

（完）
