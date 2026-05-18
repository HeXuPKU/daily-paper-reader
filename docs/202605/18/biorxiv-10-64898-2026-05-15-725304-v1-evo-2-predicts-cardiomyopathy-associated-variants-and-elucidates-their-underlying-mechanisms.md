---
title: Evo 2 Predicts Cardiomyopathy-Associated Variants and Elucidates Their Underlying Mechanisms
title_zh: Evo 2 预测心肌病相关变异并阐明其潜在机制
authors: "kurozumi, a., otsuka, n., Masamichi, I., kawakami, t., Isagawa, T., kodera, s., takeda, n."
date: 2026-05-17
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.15.725304v1.full.pdf"
tags: ["query:med-ai"]
score: 9.0
evidence: 用于预测遗传变异致病性的高分辨率基因组人工智能模型
tldr: 针对心肌病中意义不明变异（VUS）的临床解释难题，本研究评估了高分辨率基因组AI模型Evo 2的性能。通过分析ClinVar中的单核苷酸变异，Evo 2不仅在预测致病性方面表现出极高准确率（AUROC 0.983），还利用稀疏自编码器揭示了蛋白质结构域及转录因子结合位点等潜在生物学机制，为心血管遗传学提供了强大的变异评估与机制解析工具。
source: biorxiv
selection_source: fresh_fetch
motivation: 旨在解决临床上心肌病相关基因中大量意义不明变异（VUS）难以准确解释和评估的难题。
method: 采用Evo 2模型对ClinVar中的变异进行致病性预测，并结合稀疏自编码器（SAEs）分析其内部嵌入表示以提取生物学特征。
result: 模型实现了极高的预测准确率，并能识别影响蛋白质结构域及TBX5转录因子结合的关键分子机制。
conclusion: Evo 2在预测心肌病变异致病性及阐明其底层机制方面表现优异，是心血管医学领域评估VUS的强有力工具。
---

## 摘要
背景：尽管二代测序技术的进步加速了心肌病遗传变异的鉴定，但解读临床意义未明变异（VUS）仍是一项临床挑战。Evo 2 是一种高分辨率基因组人工智能模型，能够在长序列背景下预测致病性并实现机制解释；然而，其在心血管遗传学中的应用仍有限。在本研究中，我们评估了 Evo 2 在评估心肌病相关变异的致病性及其潜在机制方面的效用。方法：我们使用 Evo 2 预测了 ClinVar 数据库中列出的心肌病相关基因单核苷酸变异的致病性。我们利用嵌入（embeddings）等内部表征评估了该模型识别编码区和非编码区特征性结构特征的能力，并推断了这些区域内变异的分子机制。结果：Evo 2 在致病性预测方面表现出极高的准确性，AUROC 达到 0.983，AUPRC 达到 0.915。值得注意的是，基于嵌入的稀疏自编码器（SAEs）识别出了与高阶结构特征相对应的特征，包括心肌病相关蛋白特有的卷曲螺旋和肌动蛋白结合结构域，并准确检测到了已知会破坏这些结构域的突变。该模型通过 SAEs 识别了心脏富集转录因子 TBX5 的结合基序，并在经过监督微调后，准确预测了影响 TBX5 结合亲和力的单核苷酸多态性。结论：Evo 2 在预测致病性和提取心肌病相关变异的生物学特征方面均表现出强大的性能。它可能成为心血管医学中评估 VUS 的一种强有力的新兴工具。

## Abstract
Background: Although advances in next-generation sequencing have accelerated the identification of genetic variants in cardiomyopathy, interpreting variants of uncertain significance (VUS) remains a clinical challenge. Evo 2 is a high-resolution genomic artificial intelligence model capable of predicting pathogenicity across large sequence contexts and enabling mechanistic interpretation; however, its application in cardiovascular genetics is limited. Here, we evaluated the utility of Evo 2 for assessing the pathogenicity and underlying mechanisms of cardiomyopathy-associated variants. Methods: We used Evo 2 to predict the pathogenicity of single-nucleotide variants in cardiomyopathy-related genes listed on ClinVar. We assessed the ability of the model to identify characteristic structural features in both coding and noncoding regions using internal representation such as embeddings, and to infer the molecular mechanisms of variants within these regions. Results: Evo 2 demonstrated high predictive accuracy for pathogenicity, achieving an AUROC of 0.983 and an AUPRC of 0.915. Notably, sparse autoencoders (SAEs) from embeddings identified features corresponding to higher-order structural features, including coiled-coil and actin-binding domains characteristic of cardiomyopathy-related proteins, and accurately detected mutations known to disrupt these domains. The model recognized the binding motif of the cardiac-enriched transcription factor TBX5 with SAEs and accurately predicted a single-nucleotide polymorphism affecting TBX5 binding affinity after supervised fine-tuning. Conclusions: Evo 2 demonstrated strong performance for both predicting pathogenicity and extracting biological features of cardiomyopathy-associated variants. It may represent a powerful emerging tool for evaluating VUS in cardiovascular medicine.

---

## 论文详细总结（自动生成）

这是一份关于论文《Evo 2 Predicts Cardiomyopathy-Associated Variants and Elucidates Their Underlying Mechanisms》的结构化深度总结：

### 1. 核心问题与整体含义（研究动机和背景）
*   **核心问题**：随着二代测序（NGS）的普及，心肌病相关基因中发现了大量变异，但其中很大一部分被归类为“意义不明变异”（VUS），导致临床诊断和风险评估困难。
*   **研究背景**：现有的计算预测工具在处理长序列背景和解释非编码区变异方面存在局限。本研究旨在评估高分辨率基因组大模型 **Evo 2** 在预测心肌病致病变异及其揭示底层生物学机制（如蛋白质结构破坏或调控元件改变）方面的潜力。

### 2. 论文提出的方法论
*   **核心思想**：利用 Evo 2 这一预训练的基因组基础模型，通过其对长基因组序列的深度理解能力，实现对变异致病性的高精度预测，并结合可解释性工具分析其生物学意义。
*   **关键技术细节**：
    *   **致病性预测**：基于 Evo 2 对 ClinVar 数据库中已知致病/良性变异的序列进行评分。
    *   **特征提取（SAEs）**：引入**稀疏自编码器（Sparse Autoencoders, SAEs）**对模型的内部嵌入（Embeddings）进行分解，将高维向量转化为具有生物学意义的特征（如特定的蛋白质结构域或转录因子结合基序）。
    *   **监督微调（SFT）**：针对特定任务（如 TBX5 转录因子结合亲和力预测）对模型进行微调，以增强其在特定生物学场景下的预测精度。

### 3. 实验设计
*   **数据集**：
    *   主要使用 **ClinVar** 数据库中收录的心肌病相关基因的单核苷酸变异（SNVs）。
    *   针对非编码区，使用了涉及心脏富集转录因子 **TBX5** 结合的数据。
*   **评估指标（Benchmark）**：使用受试者工作特征曲线下面积（AUROC）和精确率-召回率曲线下面积（AUPRC）作为主要性能衡量标准。
*   **对比场景**：实验涵盖了编码区（分析蛋白质结构域如卷曲螺旋、肌动蛋白结合域）和非编码区（分析转录因子结合位点）。

### 4. 资源与算力
*   **算力说明**：论文摘要及元数据中**未明确说明**具体的 GPU 型号、数量或训练时长。通常此类大规模基因组模型的推理和微调需要高性能计算资源（如 NVIDIA A100 或 H100 集群）。

### 5. 实验数量与充分性
*   **实验规模**：研究进行了多维度的验证，包括：
    1.  大规模 ClinVar 变异的致病性分类实验。
    2.  利用 SAEs 识别蛋白质高阶结构特征的定性分析。
    3.  针对 TBX5 结合亲和力的专项预测实验。
*   **充分性评价**：实验设计较为全面，不仅关注预测准确率（0.983 AUROC），还深入探讨了模型如何“理解”生物学特征，通过 SAEs 建立了模型内部表示与已知生物学结构（如卷曲螺旋）之间的联系，具有较强的说服力。

### 6. 主要结论与发现
*   **高精度预测**：Evo 2 在心肌病变异预测中表现极佳，AUROC 达到 **0.983**，AUPRC 达到 **0.915**。
*   **机制解析**：模型能够识别出心肌病蛋白的关键结构域（如肌动蛋白结合域），并能准确检测到破坏这些结构域的突变。
*   **非编码区洞察**：Evo 2 能够识别 TBX5 等关键转录因子的结合基序，并在微调后准确预测影响结合亲和力的非编码 SNVs。
*   **临床价值**：Evo 2 有望成为评估心血管领域 VUS 的强有力工具。

### 7. 优点
*   **高分辨率与长背景**：相比传统模型，Evo 2 能处理更长的序列背景，捕捉复杂的基因组相互作用。
*   **强大的可解释性**：通过 SAEs 技术，成功将深度学习的“黑箱”表示转化为可理解的生物学特征（结构域、基序）。
*   **跨区域应用**：同时适用于编码区和非编码区，为全基因组关联研究（GWAS）后的变异功能解释提供了统一框架。

### 8. 不足与局限
*   **数据依赖性**：模型性能高度依赖于 ClinVar 等数据库的标注质量，可能存在标注偏差（Annotation Bias）。
*   **变异类型限制**：研究重点在于单核苷酸变异（SNVs），对于插入、缺失（Indels）或大规模结构变异（SVs）在心肌病中的表现尚需进一步验证。
*   **临床转化路径**：虽然预测准确率高，但如何将 AI 评分整合进现有的 ACMG/AMP 变异分类指南仍需临床共识和更多前瞻性研究。

（完）
