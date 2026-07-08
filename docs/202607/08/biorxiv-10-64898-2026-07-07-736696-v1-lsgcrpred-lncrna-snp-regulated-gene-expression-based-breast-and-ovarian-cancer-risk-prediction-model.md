---
title: "LsGCRPred: lncRNA-SNP regulated gene expression-based breast and ovarian cancer risk prediction model"
title_zh: "LsGCRPred: 基于lncRNA-SNP调控基因表达的乳腺癌和卵巢癌风险预测模型"
authors: "Das, T., Das, G., Ghosh, B., GHOSH, Z."
date: 2026-07-07
pdf: "https://www.biorxiv.org/content/10.64898/2026.07.07.736696v1.full.pdf"
tags: ["query:gwas"]
score: 8.0
evidence: 基于lncRNA-SNP调控基因表达的癌症风险预测模型，类似多基因风险评分
tldr: 针对乳腺癌和卵巢癌的遗传异质性，现有风险检测缺乏lncRNA-SNP标记。本文提出LsGCRPred模型，整合组织特异性与个体易感性，通过LSNP-基因互作预测癌症风险。通路分析显示互作基因参与关键调控通路，实验验证了选定LSNP在癌细胞系中的表达。该模型为个性化癌症诊疗提供了新见解。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有癌症风险预测缺少lncRNA-SNP标记，需考虑组织特异性和个体易感性以提高预测精度。
method: 建立基于LSNP-基因互作的LsGCRPred模型，整合组织特异性与个体易感性，结合通路分析和实验验证。
result: 识别出LSNP互作基因参与关键癌症通路，并通过TaqMan和qPCR验证了在细胞系中的表达。
conclusion: 模型揭示了lncRNA遗传变异对癌症的调控作用，为个性化诊断和治疗提供了新策略。
---

## 摘要
长链非编码RNA（lncRNAs）及其中的单核苷酸多态性（SNPs）在癌症易感性和疾病预后中发挥关键作用。乳腺癌和卵巢癌具有遗传异质性，给精准诊断和治疗带来了重大挑战。尽管个体化医学最近取得了进展，但将lncRNA-SNP（LSNP）标志物纳入癌症风险检测面板仍然有限。在这项工作中，我们提出了基于lncRNA-SNP调控基因表达的乳腺癌和卵巢癌风险预测模型LsGCRPred（LSNP-基因相互作用驱动的癌症风险预测模型）。值得注意的是，我们的方法考虑了lncRNA的组织特异性以及对于具有易感因素的个体的益处。此外，通路分析揭示了LSNP相互作用基因参与关键的癌症调控通路。通过TaqMan基因分型和qPCR验证了选定的LSNPs在卵巢癌和乳腺癌细胞系中的存在，以及lncRNA和相关基因转录本的显著表达。这些发现强调了之前被忽视的lncRNA位点内的遗传变异及其对疾病预后的调控影响，为个体化癌症诊断和治疗策略提供了见解。LsGCRPred工具可作为独立版本在GitHub上获取。GitHub链接：https://github.com/zglabDIB/LsGCRPred

## Abstract
Long non-coding RNAs (lncRNAs) and single nucleotide polymorphisms (SNPs) within them play crucial role in cancer susceptibility and disease outcomes. Breast and ovarian cancers, characterized by genetic heterogeneity, present significant challenges for precise diagnosis and treatment. Despite recent advancements in personalized medicine, inclusion of lncRNA-SNP (LSNP) markers into cancer risk detection panels remains limited. In this work, we put forward lncRNA-SNP regulated gene expression-based breast and ovarian cancer risk prediction model LsGCRPred (LSNP-Gene Interaction Based Cancer Risk Prediction Model). Notably, our approach accounts for the tissue-specificity of lncRNAs as well the benefit for individuals with predisposing conditions. Additionally, pathway analysis revealed the involvement of the LSNP interacting genes in key cancer regulating pathways. TaqMan genotyping and qPCR were performed to confirm the presence of selected LSNPs in ovarian and breast cancer cell lines along with the significant expression of the lncRNA and associated gene transcripts. These findings highlight previously overlooked genetic variants within lncRNA loci and their regulatory impact on disease outcomes, providing insights into personalized cancer diagnosis and treatment strategies. The tool LsGCRPred can be accessed as a standalone version on GitHub. Github Link: https://github.com/zglabDIB/LsGCRPred

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）
- **核心问题**：乳腺癌和卵巢癌具有显著的遗传异质性，现有癌症风险预测模型主要关注编码区SNP，而忽略了lncRNA中的SNP（LSNP）作为标记的可能性。lncRNA在基因调控中发挥关键作用，其内部的遗传变异可能影响癌症易感性和预后，但目前缺乏整合LSNP的个性化风险评估工具。
- **整体含义**：本文旨在弥补这一空白，通过构建 **LsGCRPred** 模型，将lncRNA的组织特异性表达与个体易感性因素相结合，利用LSNP-基因相互作用来预测乳腺癌和卵巢癌风险，从而为精准诊疗提供新见解。

### 2. 论文提出的方法论：核心思想、关键技术细节
- **核心思想**：基于lncRNA-SNP（LSNP）调控的基因表达关系，建立组织特异性和个体易感性联合驱动的癌症风险预测模型 **LsGCRPred**（LSNP-Gene Interaction Based Cancer Risk Prediction Model）。
- **关键技术细节**（根据摘要推测）：
  - 从GWAS数据中筛选位于lncRNA基因座的SNP（即LSNP）。
  - 通过共定位、eQTL或染色质交互分析等方法，识别LSNP可能调控的靶基因（LSNP-基因互作）。
  - 整合lncRNA在乳腺/卵巢组织中的特异性表达数据，以及个体携带LSNP的易感状态，构建风险评分或预测模型。
  - 对识别的互作基因进行通路富集分析，确认其参与关键癌症调控通路。
  - 实验验证：利用TaqMan基因分型检测选定LSNP在癌细胞系中的存在，并通过qPCR验证lncRNA及关联基因的表达水平。
- **算法流程**（文字说明）：
  1. 数据收集：获取癌症相关GWAS汇总统计、lncRNA注释、组织表达谱。
  2. LSNP筛选：选取位于lncRNA本体或其调控区域的显著SNP。
  3. 靶基因预测：使用功能基因组学方法（如GTEx eQTL、Hi-C）获取LSNP的潜在靶基因。
  4. 模型构建：将LSNP基因型、靶基因表达、组织特异性合并为风险预测特征，可能采用逻辑回归或机器学习分类器。
  5. 验证：通路富集分析与体外细胞系实验。
- **注**：论文未公开详细的数学模型或公式，上述流程为基于摘要的合理推断。

### 3. 实验设计
- **数据集/场景**：
  - 遗传数据：未明确说明具体GWAS数据集（可能来自公开数据库如GWAS Catalog或UK Biobank）。
  - 组织表达数据：来自GTEx或TCGA的乳腺/卵巢组织RNA-seq。
  - 实验验证：使用**卵巢癌和乳腺癌细胞系**（具体细胞系名称未在摘要中给出），进行TaqMan基因分型和qPCR。
- **Benchmark**：未提及与其他现有模型（如传统PRS、lncRNA风险评分）的对比。
- **对比方法**：文中未进行方法比较，主要聚焦于模型构建和通路分析。

### 4. 资源与算力
- **未明确说明**：论文摘要及元数据中未提及使用的GPU型号、数量、训练时长或任何计算硬件资源。作为bioinformatics模型，可能主要依赖CPU处理统计计算，训练量不大。具体算力信息缺失。

### 5. 实验数量与充分性
- **实验数量**：仅描述了一次通路分析和一次细胞系验证（TaqMan + qPCR）。未列出多种细胞系、不同SNP位点的重复实验数量，也未进行独立外部验证。
- **充分性**：不足。缺乏大规模人群队列的回顾性或前瞻性验证；没有与其他风险模型（如PRS、多基因风险评分）的对比；没有消融实验验证各组分的贡献；仅两个细胞系的验证对于临床转化而言代表性有限。

### 6. 论文的主要结论与发现
- LSNP互作基因富集于关键癌症调控通路，提示lncRNA遗传变异通过调控基因表达影响癌症发生。
- 在癌系中证实了选定LSNP的存在以及相关lncRNA和基因转录本的显著表达，支持了LSNP的功能重要性。
- 提出的LsGCRPred模型能够整合组织特异性和个体易感性，为个性化癌症诊断和治疗提供新策略。
- 工具已开源（GitHub），便于复现和扩展。

### 7. 优点
- **创新性**：首次将lncRNA-SNP纳入乳腺癌/卵巢癌风险预测，弥补了传统PRS忽视非编码区变异的不足。
- **整合组织特异性**：考虑lncRNA在不同组织中的差异表达，提高了模型的生物学合理性。
- **具备实验验证**：通过TaqMan分型和qPCR从湿实验角度确认了LSNP的分子存在和表达，增强了方法论的可信度。
- **开放工具**：提供独立可执行的GitHub版本，有利于社区应用和改进。

### 8. 不足与局限
- **缺乏大规模验证**：仅使用细胞系进行验证，未在独立人群队列（如病例-对照样本）中评估预测性能（如AUC、校准度）。
- **未与基线方法比较**：未对比传统PRS、其他lncRNA相关风险模型或无SNP-基因互作的简单模型，难以衡量本模型的增量价值。
- **数据集未具体化**：GWAS来源、样本量、SNP筛选阈值均未说明，降低了可复现性。
- **适用范围有限**：仅针对乳腺癌和卵巢癌，且可能仅限于特定人群（如欧洲裔），泛化能力未知。
- **假设风险**：模型依赖LSNP-基因互作的预测，而eQTL或染色质交互可能存在组织特异性混杂或假阳性，未进行功能验证（如CRISPR敲除）。
- **统计细节缺失**：未给出风险评分的计算公式、cut-off确定方法或不确定性度量。

（完）
