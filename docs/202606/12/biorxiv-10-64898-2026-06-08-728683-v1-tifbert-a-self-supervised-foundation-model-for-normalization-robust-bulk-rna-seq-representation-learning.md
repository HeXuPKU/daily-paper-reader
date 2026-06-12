---
title: "TifBERT: a self-supervised foundation model for normalization-robust bulk RNA-seq representation learning"
title_zh: TifBERT：一种用于归一化鲁棒的大批量RNA-seq表示学习的自监督基础模型
authors: "Hosseini, S., Sharma, D."
date: 2026-06-11
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.08.728683v1.full.pdf"
tags: ["query:med-ai"]
score: 6.0
evidence: 用于bulk RNA-seq的自监督基础模型，属于大规模基因组模型方向
tldr: "针对bulk RNA-seq现有方法依赖表达离散化或基因集限制的问题，提出TifBERT自监督框架。该方法通过TF-IDF排序将表达谱转为基因序列，采用掩码基因建模预训练，无需外部嵌入。在33种TCGA癌症中达90.83%准确率，GTEx组织结构保存完好，嵌入有效秩达95.6，显著优于现有模型，实现归一化稳健的转录组表示学习。"
source: biorxiv
selection_source: fresh_fetch
motivation: 现有bulk RNA-seq基础模型依赖表达离散化、外部嵌入或限制基因集，导致不同归一化方案和队列间鲁棒性差。
method: TifBERT将无序表达谱经TF-IDF排序转为基因序列，通过掩码基因建模（预测基因身份）进行自监督预训练，不使用表达式重建。
result: "33种TCGA癌症分类准确率90.83%，AUC-ROC 0.996，MCC 0.903；通路Pearson相关系数0.754-0.762；GTEx无需微调保持组织结构；嵌入有效秩95.6。"
conclusion: TifBERT是一种可扩展、归一化无关的基础模型，用于可复用的bulk转录组表示学习，性能与稳定性优于现有方法。
---

## 摘要
大批量RNA测序仍然是转化基因组学的核心，然而基础模型的发展主要集中在单细胞数据上。现有的用于大批量RNA-seq的Transformer方法通常依赖于表达离散化、数值重构、外部基因嵌入或受限基因集，这限制了跨归一化方案和队列的鲁棒性。在这里，我们介绍了TifBERT，一个用于全转录组大批量RNA-seq表示学习的自监督框架。TifBERT使用词频-逆文档频率（TF-IDF）排序将每个无序表达谱转换为样本特异性基因序列，优先考虑在样本中高表达且在队列中选择性表达的基因。然后通过掩码基因建模进行预训练，从转录组背景中预测基因身份，而不是重构表达值。在涵盖五种RNA-seq归一化方案的统一TCGA泛癌数据上预训练后，TifBERT学习了大约10,000个基因的上下文表示，无需表达分箱、标志基因限制或外部生物嵌入。在33种TCGA癌症类型中，TifBERT达到了90.83%的准确率、0.996的宏AUC-ROC和0.903的MCC。它还捕捉了通路水平的生物学特征，在1,387个PARADIGM通路活性上实现了平均样本-wise和通路-wise Pearson相关系数分别为0.754和0.762。在GTEx健康组织上的独立评估显示，无需再训练即可保持组织水平的转录组结构。与现有模型相比，TifBERT实现了具有显著更高稳定性的竞争性子型判别，并产生了更丰富的嵌入几何结构（有效秩95.6对比6.3），无需表达离散化或分布内预训练暴露。总之，TifBERT为可重用的批量转录组表示学习提供了一个可扩展的、与归一化无关的基础模型。

## Abstract
Bulk RNA sequencing remains central to translational genomics, yet foundation-model development has largely focused on single-cell data. Existing transformer approaches for bulk RNA-seq often rely on expression discretization, numerical reconstruction, external gene embeddings, or restricted gene sets, limiting robustness across normalization schemes and cohorts. Here, we introduce TifBERT, a self-supervised framework for full-transcriptome bulk RNA-seq representation learning. TifBERT converts each unordered expression profile into a sample-specific gene sequence using term frequency-inverse document frequency (TF-IDF) ordering, prioritizing genes that are both highly expressed within a sample and selectively expressed across the cohort. It is then pretrained using masked gene modeling, predicting gene identities from transcriptomic context rather than reconstructing expression values. Pretrained on harmonized TCGA Pan-Cancer data spanning five RNA-seq normalization schemes, TifBERT learns contextual representations across approximately 10,000 genes without expression binning, landmark-gene restriction, or external biological embeddings. Across 33 TCGA cancer types, TifBERT achieved 90.83% accuracy, 0.996 macro AUC-ROC, and 0.903 MCC. It also captured pathway-level biology, achieving mean sample-wise and pathway-wise Pearson correlations of 0.754 and 0.762 across 1,387 PARADIGM pathway activities. Independent evaluation on GTEx healthy tissues showed preservation of tissue-level transcriptomic structure without retraining. In comparison with existing models, TifBERT achieves competitive subtype discrimination with substantially greater stability and produces markedly richer embedding geometry (effective rank 95.6 versus 6.3), without requiring expression discretization or in-distribution pretraining exposure. Together, TifBERT provides a scalable, normalization-independent foundation model for reusable bulk transcriptomic representation learning