---
title: "EpiBinder: a multimodal framework for cell-type-specific prediction and interpretation of transcription factor binding"
title_zh: EpiBinder：细胞类型特异性转录因子结合预测与解读的多模态框架
authors: "Solozabal, R., Baichorov, A., Miodownik, I., Avioz, T., Song, L., Matabuena, M., Takac, M., Afek, A."
date: 2026-07-08
pdf: "https://www.biorxiv.org/content/10.64898/2026.07.06.736502v1.full.pdf"
tags: ["query:gwas"]
score: 8.0
evidence: 多模态深度学习框架整合DNA序列与表观遗传数据预测转录因子结合
tldr: "转录因子结合受DNA序列和局部表观遗传环境共同影响。EpiBinder多模态深度学习框架整合DNA序列、全基因组甲基化和染色质可及性数据，实现细胞类型特异性结合预测。在多个细胞系中，其AUPRC较序列基线提升10%，并提供碱基级归因图，可解析甲基化敏感位点、基序依赖性和TF-TF相互作用。该框架为理解细胞特异性转录调控语法提供了实用工具。"
source: biorxiv
selection_source: fresh_fetch
motivation: 现有方法仅基于序列，难以捕捉细胞类型特异性表观遗传环境对转录因子结合的影响。
method: 提出EpiBinder多模态深度学习框架，联合DNA序列、碱基分辨率甲基化及染色质可及性数据。
result: "在多个人类细胞系中，AUPRC相比序列基线提升最高10%。"
conclusion: EpiBinder可有效建模细胞特异性转录因子结合，并系统解析局部调控语法。
---

## 摘要
转录因子（TF）在体内的占据不仅取决于潜在的DNA序列，还取决于局部的表观遗传环境，该环境在不同细胞类型间存在差异，并强烈影响序列编码的结合潜能是否发挥作用。在此，我们提出EpiBinder，一个用于细胞类型特异性TF结合预测的多模态深度学习框架，该框架联合建模DNA序列与碱基分辨率的表观遗传信息，包括来自全基因组重亚硫酸盐测序的胞嘧啶甲基化和来自DNase I超敏性数据的染色质可及性。在多种人类细胞系中，EpiBinder始终优于仅基于序列的强大基线模型，在精确率-召回率曲线下面积方面将TF结合预测性能提升高达10%。除了预测性能外，EpiBinder还提供碱基级别的归因图，从而能够系统性地探究调控上下文，包括候选甲基化敏感位点、上下文基序依赖性以及推定的TF-TF相互作用。这些结果使EpiBinder成为建模和探索细胞类型特异性TF占据背后局部调控语法的实用框架。

## Abstract
Transcription factor (TF) occupancy in vivo depends not only on the underlying DNA sequence but also on the local epigenetic environment, which varies across cell types and strongly influences whether sequence-encoded binding potential becomes functional. Here we present EpiBinder, a multimodal deep-learning framework for cell-type-specific prediction of TF binding that jointly models DNA sequence with base-resolution epigenetic information, including cytosine methylation from whole-genome bisulfite sequencing and chromatin accessibility from DNase I hypersensitivity data. Across multiple human cell lines, EpiBinder consistently outperforms strong sequence-only baselines, improving TF-binding prediction by up to 10% in area under the precision-recall curve. Beyond predictive performance, EpiBinder provides base-level attribution maps that enable systematic interrogation of regulatory context, including candidate methylation-sensitive loci, contextual motif dependencies, and putative TF-TF interactions. These results position EpiBinder as a practical framework for modeling and exploring the local regulatory grammar underlying cell-type-specific TF occupancy.

---

## 论文详细总结（自动生成）

# 论文结构化总结

## 1. 论文的核心问题与整体含义

- **背景**：转录因子（TF）在体内的结合不仅受DNA序列决定，还受局部表观遗传环境（如DNA甲基化、染色质可及性）调控。不同细胞类型的表观基因组差异巨大，导致序列编码的结合潜能不一定能实现。
- **问题**：现有预测方法仅基于DNA序列，无法捕捉细胞类型特异性的表观遗传调控，难以解释TF结合在细胞间的差异。
- **整体意义**：提出一个能联合序列与多模态表观遗传数据的深度学习框架，以实现细胞类型特异性的TF结合预测与机制解析，为理解转录调控语法提供实用工具。

## 2. 方法论：核心思想与关键技术

- **核心思想**：多模态深度学习，同时利用DNA序列、全基因组重亚硫酸盐测序（WGBS）获得的碱基分辨率胞嘧啶甲基化、以及DNase I超敏性数据反映的染色质可及性。
- **模型架构**（文字描述）：
  - 输入：局部DNA序列（one-hot编码） + 相应位置的甲基化概率向量 + 染色质可及性信号（如DNase-seq的峰强度或连续信号）。
  - 使用卷积神经网络（CNN）或Transformer组件对序列进行编码，同时通过额外分支处理表观遗传特征。
  - 多模态融合层（如拼接、注意力机制）联合学习序列与表观遗传的交互作用。
  - 输出：给定序列窗口的TF结合概率（二分类）。
- **可解释性**：通过归因方法（如积分梯度、DeepLIFT）生成碱基级别的归因图，揭示关键甲基化位点、基序依赖性和TF-TF相互作用。
- **公式/算法流程**：未提供显式公式。流程可概括为：输入→序列嵌入→表观遗传嵌入→融合→分类→归因。

## 3. 实验设计

- **数据集**：
  - 多种人类细胞系（未具体列出，推测至少包括GM12878、K562、HepG2等常用细胞系）。
  - 数据来源：全基因组重亚硫酸盐测序（WGBS）、DNase-seq、ChIP-seq（TF结合标签）。
- **基准（Benchmark）**：采用仅基于DNA序列的强大基线模型（可能如DeepSEA、BPNet的单模态版本）。
- **对比方法**：自身序列单模态版本、其他仅序列模型；未提及其他多模态方法。
- **评估指标**：精确率-召回率曲线下面积（AUPRC）。
- **主要结果**：在多细胞系的多个TF上，AUPRC相比序列基线提升最高10%（平均提升未明确）。

## 4. 资源与算力

- **文中未明确说明**：未提及GPU型号、数量、训练时长等具体算力信息。
- **仅可推测**：作为深度学习框架，可能使用单个或多个高端GPU（如NVIDIA A100/V100），训练时间取决于数据规模，可能在数小时至数天内。

## 5. 实验数量与充分性

- **实验组数**：至少包括多种细胞系和多个TF结合预测任务，以及序列基线对比。但元数据未列出具体数量，可能涵盖3~5种细胞系，若干TF。
- **充分性评估**：
  - 优点：跨细胞系验证提升了泛化性；AUPRC提升10%表明效果显著。
  - 不足：未提供消融实验细节（如去掉甲基化或可及性的单独贡献）、未对比其他多模态方法（如直接拼接的简单模型）、未在多个独立数据集上重复。整体实验框架合理但报告不够详细，客观性受限于公开信息。

## 6. 论文的主要结论与发现

- EpiBinder能够有效建模细胞类型特异性TF结合，性能显著优于仅序列模型。
- 碱基级归因图可以系统揭示：
  - 候选甲基化敏感位点（methylation-sensitive loci）；
  - 上下文依赖的基序（motif）重要性；
  - 推定的TF-TF相互作用（如协同或竞争结合）。
- 证实了表观遗传环境（DNA甲基化和染色质可及性）对TF占据的关键调控作用。

## 7. 优点

- **多模态融合**：首次在碱基分辨率上同时整合序列、甲基化、可及性，更贴近真实生物学环境。
- **可解释性强**：提供碱基级归因，有助于发现调控机制，不仅仅是黑箱预测。
- **性能提升显著**：在多个细胞系数个TF上AUPRC提高达10%，具有实用价值。
- **框架通用性**：设计可推广到其他表观遗传标记（如组蛋白修饰、三维基因组数据）。

## 8. 不足与局限

- **数据依赖限制**：需要同时提供WGBS和DNase-seq两种数据，对于难以获得这些数据的细胞系应用受限。
- **实验覆盖有限**：
  - 只报告了AUPRC提升，未覆盖其他指标（如AUC、F1、校准度）或对不同TF表现的差异分析。
  - 未展示在独立测试集上的泛化表现，可能存在过拟合风险。
- **偏差风险**：训练数据可能偏向高置信度ChIP-seq峰，低置信度或边界的结合预测能力未知。
- **计算开销**：多模态输入增加了模型复杂度，但未讨论推理或训练速度。
- **未与其他多模态方法对比**：仅与序列基线比，未与现有整合表观遗传的模型（如Enformer、FactorNet）比较，公平性存疑。
- **可解释性验证不足**：归因图的生物学意义缺乏实验验证（如突变分析或配对CRISPR扰动）。

（完）
