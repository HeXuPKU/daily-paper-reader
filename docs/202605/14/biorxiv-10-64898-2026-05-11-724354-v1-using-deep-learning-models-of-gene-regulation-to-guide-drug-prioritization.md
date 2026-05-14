---
title: Using Deep Learning Models of Gene Regulation to Guide Drug Prioritization
title_zh: 利用基因调控深度学习模型指导药物优先级排序
authors: "Ovcharenko, I., Huang, X."
date: 2026-05-14
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.11.724354v1.full.pdf"
tags: ["query:gwas"]
score: 9.0
evidence: 将GWAS非编码变体与基因调节和药物优先级联系起来的深度学习框架
tldr: "该研究开发了一个整合深度学习框架，旨在通过模拟非编码区遗传变异来指导药物重定位。由于90%以上的GWAS风险变异位于非编码区，研究通过等位基因特异性增强子预测，将调控变异与转录因子（如FOXA1）驱动的基因表达变化及药物诱导的转录谱相结合。以乳腺癌为案例，成功识别出包括氟维司群在内的63种候选药物，为从非编码基因组挖掘治疗方案提供了通用策略。"
source: biorxiv
selection_source: fresh_fetch
motivation: "现有的药物重定位方法大多忽略了占GWAS风险变异90%以上的非编码区调控变异，导致难以将遗传发现转化为治疗方案。"
method: 开发了一种整合深度学习框架，通过预测等位基因特异性增强子活性，关联转录因子介导的基因表达变化与药物诱导的转录谱。
result: "在乳腺癌研究中识别出受FOXA1调控的关键变异，并筛选出63种候选化合物，其中54%的药物在核心通路中表现出显著的转录拮抗作用。"
conclusion: 该研究建立了一个由调控变异引导的药物重定位框架，有效地将非编码遗传变异转化为具有药理学意义的治疗假设。
---

## 摘要
药物重定向（Drug repurposing）为加速治疗发现提供了一种具有成本效益的策略，但大多数计算方法未能对非编码遗传变异进行建模。由于超过 90% 的全基因组关联研究（GWAS）风险变异位于非编码区，将调控变异与治疗假设联系起来仍然是一项重大挑战。在此，我们开发了一个综合深度学习框架，该框架将等位基因特异性增强子预测与以转录因子（TF）为中心的基因表达变化以及药物诱导的转录谱联系起来，以对候选治疗药物进行优先级排序。我们的细胞类型特异性深度学习增强子模型能够准确区分七种细胞系中的活性增强子。以乳腺癌作为概念验证，我们发现 GWAS 遗传力在 MCF7 增强子中显著富集，支持 MCF7 作为该疾病的细胞背景。等位基因特异性变异评分识别出了具有强等位基因依赖性效应的乳腺癌风险变异，基于归因的基序（motif）发现揭示了 FOXA1 相关基序特征的富集，这与原发肿瘤中 FOXA1 的上调一致。整合 FOXA1 敲低诱导的和药物诱导的基因表达谱，识别出 63 种治疗乳腺癌的候选化合物，其中包括 18 种已批准药物，并找回了已知的乳腺癌治疗药物氟维司群（fulvestrant）。在优先排序的化合物中，54% 在八条核心乳腺癌通路中表现出反相关的转录效应，而未优先排序的化合物中这一比例仅为 5.3%。药物-基因相互作用数据的整合进一步将这些化合物精炼为 8 种具有实验或临床证据支持的化合物。总之，这些结果建立了一个由调控变异引导的药物重定向框架，将非编码遗传变异与候选治疗药物联系起来，并为将非编码基因组转化为药理学相关假设提供了一种可推广的策略。

## Abstract
Drug repurposing offers a cost-effective strategy to accelerate therapeutic discovery, but most computational approaches fail to model noncoding genetic variation. Because over 90% of genome-wide association study (GWAS) risk variants reside in noncoding regions, linking regulatory variation to therapeutic hypotheses remains a major challenge. Here, we developed an integrative deep learning framework that links allele-specific enhancer prediction to transcription factor (TF)-centered gene expression changes and drug-induced transcriptional profiles to prioritize candidate therapeutics. Our cell type-specific deep learning enhancer models accurately distinguish active enhancers across seven cell lines. Using breast cancer as a proof-of-concept, we found that GWAS heritability is significantly enriched in MCF7 enhancers, supporting MCF7 as the cellular context for this disease. Allele-specific variant scoring identified breast cancer risk variants with strong allele-dependent effects, and attribution-based motif discovery revealed enrichment of FOXA1-associated motif features, consistent with FOXA1 upregulation in primary tumors. Integration of the FOXA1 knockdown-induced and drug-induced gene expression profiles identified 63 candidate compounds for treatment of breast cancer, including 18 approved drugs, with recovery of the known breast cancer therapy fulvestrant. Among prioritized compounds, 54% showed anti-correlated transcriptional effects across eight core breast cancer pathways, compared to 5.3% of non-prioritized compounds. Integration of drug-gene interaction data further refined these to eight compounds with supporting experimental or clinical evidence. Together, these results establish a regulatory variant-guided drug repurposing framework that connects noncoding genetic variation to therapeutic candidates and provides a generalizable strategy for translating the noncoding genome into pharmacologically relevant hypotheses.Drug repurposing offers a cost-effective strategy to accelerate therapeutic discovery, but most computational approaches fail to model noncoding genetic variation. Because over 90% of genome-wide association study (GWAS) risk variants reside in noncoding regions, linking regulatory variation to therapeutic hypotheses remains a major challenge. Here, we developed an integrative deep learning framework that links allele-specific enhancer prediction to transcription factor (TF)-centered gene expression changes and drug-induced transcriptional profiles to prioritize candidate therapeutics. Our cell type-specific deep learning enhancer models accurately distinguish active enhancers across seven cell lines. Using breast cancer as a proof-of-concept, we found that GWAS heritability is significantly enriched in MCF7 enhancers, supporting MCF7 as the cellular context for this disease. Allele-specific variant scoring identified breast cancer risk variants with strong allele-dependent effects, and attribution-based motif discovery revealed enrichment of FOXA1-associated motif features, consistent with FOXA1 upregulation in primary tumors. Integration of the FOXA1 knockdown-induced and drug-induced gene expression profiles identified 63 candidate compounds for treatment of breast cancer, including 18 approved drugs, with recovery of the known breast cancer therapy fulvestrant. Among prioritized compounds, 54% showed anti-correlated transcriptional effects across eight core breast cancer pathways, compared to 5.3% of non-prioritized compounds. Integration of drug-gene interaction data further refined these to eight compounds with supporting experimental or clinical evidence. Together, these results establish a regulatory variant-guided drug repurposing framework that connects noncoding genetic variation to therapeutic candidates and provides a generalizable strategy for translating the noncoding genome into pharmacologically relevant hypotheses.

---

## 论文详细总结（自动生成）

这篇论文介绍了一个名为“调控变异引导的药物重定位”的综合深度学习框架。以下是对该论文的结构化总结：

### 1. 核心问题与整体含义（研究动机和背景）
*   **核心问题**：传统的药物研发成本高、周期长且成功率低。虽然药物重定位（Drug Repurposing）提供了捷径，但现有的计算方法大多依赖于蛋白质编码基因或网络分析，忽略了占 GWAS（全基因组关联研究）风险变异 90% 以上的**非编码区（Noncoding）遗传变异**。
*   **研究动机**：如何将这些位于增强子等调控元件中的非编码变异，转化为可解释的生物学机制（如转录因子调控变化），并以此指导药物的优先级排序，是当前精准医疗和药物发现中的重大挑战。

### 2. 论文提出的方法论
该框架整合了深度学习、功能基因组学和转录组学数据，主要流程如下：
*   **增强子建模**：利用 **TREDNet**（一个两阶段深度学习框架）对特定细胞系的增强子进行建模。第一阶段在大规模基因组数据上预训练，第二阶段针对特定细胞系（如 MCF7）的染色质开放性（ATAC-seq/DNase-seq）和 H3K27ac 信号进行微调。
*   **等位基因特异性评分**：计算 GWAS 风险等位基因与保护性等位基因之间的增强子预测得分差异（$\Delta score$），识别具有强调控效应的候选变异。
*   **基序（Motif）发现与转录因子（TF）推断**：使用 **DeepLIFT** 归因方法和 **TF-MoDISco** 识别受风险变异影响的关键 TF 基序。
*   **转录一致性匹配**：
    *   从 **KnockTF 2.0** 获取 TF 敲低（Knockdown）后的差异表达谱。
    *   从 **LINCS L1000** 获取药物诱导的基因表达谱。
    *   **公式化评分**：定义“TF 敲低一致性得分”（KD concordance），计算药物诱导的基因变化与 TF 敲低特征之间的方向一致性。
*   **通路与相互作用精炼**：通过计算药物与疾病通路（如 TCGA 乳腺癌数据）的转录反相关性，并结合 **DGIdb 5.0** 的药物-基因相互作用数据，对候选药物进行分层（Tier 1-3）。

### 3. 实验设计
*   **数据集**：
    *   **表观基因组**：ENCODE 的 7 种细胞系（A673, HCT116, HepG2, IMR90, K562, MCF7, PC3）。
    *   **遗传学**：135 项 GWAS 研究，涵盖 42 种性状。
    *   **转录组**：LINCS L1000（药物）、KnockTF 2.0（TF 扰动）、TCGA-BRCA（乳腺癌肿瘤数据）。
*   **概念验证场景**：以**乳腺癌**和 **MCF7 细胞系**作为主要案例。
*   **Benchmark 与对比**：
    *   验证模型是否能找回已知的乳腺癌药物（如氟维司群）。
    *   对比优先排序化合物与非优先排序化合物在核心生物通路（如 E2F 靶点、G2M 检查点）中的表现。
    *   使用 5000 次随机基因集置换检验（Permutation Test）作为统计基准。

### 4. 资源与算力
*   论文提到使用了 **NIH HPC Biowulf 集群**进行计算。
*   **未明确说明**具体的 GPU 型号、数量以及训练的具体时长。但考虑到 TREDNet 的两阶段架构和多细胞系微调，该过程涉及大规模的深度学习训练。

### 5. 实验数量与充分性
*   **实验规模**：分析了 7 种细胞系，训练了相应的增强子模型（AUROC 0.91-0.98），处理了超过 2 万个乳腺癌相关变异。
*   **充分性**：研究不仅停留在模型预测，还通过 TCGA 临床数据验证了推断出的 TF（如 FOXA1）在肿瘤中的表达情况。
*   **客观性**：采用了严格的统计过滤（如 FDR 校正、置换检验），并结合了第三方数据库（DGIdb）进行独立验证，实验设计较为全面且逻辑自洽。

### 6. 主要结论与发现
*   **FOXA1 是核心驱动者**：乳腺癌风险变异显著富集在 FOXA1 相关基序上，且 FOXA1 在乳腺癌肿瘤中显著上调。
*   **药物筛选结果**：识别出 63 种候选化合物，其中 18 种为已批准药物。成功找回了氟维司群（Fulvestrant）。
*   **通路拮抗效应**：54% 的优先排序化合物在 8 条乳腺癌核心通路上表现出显著的转录反相关（拮抗）作用，远高于背景水平（5.3%）。
*   **精选名单**：最终确定了 8 种具有强有力证据的候选药物，包括伊沙佐米（Ixazomib）、匹伐他汀（Pitavastatin）等。

### 7. 优点（亮点）
*   **跨领域整合**：成功将深度学习预测的非编码调控效应与药理学转录响应联系起来，填补了 GWAS 到药物发现之间的鸿沟。
*   **可解释性强**：通过 TF 扰动谱作为中介，解释了药物为何可能有效（即模拟了致病 TF 的抑制效果）。
*   **通用性**：框架不局限于乳腺癌，可推广至任何具有匹配表观基因组和转录组数据的复杂疾病。

### 8. 不足与局限
*   **缺乏湿实验验证**：所有结论均基于计算推断，尚未进行体外或体内的生物学实验验证。
*   **数据依赖性**：该方法高度依赖于高质量的 TF 扰动数据和药物转录谱，对于缺乏这些数据的细胞类型或疾病无法应用。
*   **细胞系偏差**：使用癌症衍生细胞系（如 MCF7）可能无法完全模拟生殖系变异在正常组织中的调控动态。
*   **数据库局限**：药物-基因相互作用数据库（如 DGIdb）可能存在注释不全或缺乏细胞特异性的问题。

（完）
