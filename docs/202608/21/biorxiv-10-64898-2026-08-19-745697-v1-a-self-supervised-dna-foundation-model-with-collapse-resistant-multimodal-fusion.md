---
title: A self-supervised DNA foundation model with collapse-resistant multimodal fusion
title_zh: 一种具有抗崩溃多模态融合的自监督DNA基础模型
authors: "Chen, Y."
date: 2026-08-20
pdf: "https://www.biorxiv.org/content/10.64898/2026.08.19.745697v1.full.pdf"
tags: ["query:med-ai"]
score: 8.0
evidence: 自监督DNA基础模型与多模态融合，直接对应复合主题中的基因组大模型
tldr: 现有基因组基础模型仅基于DNA序列进行预训练，难以充分捕获染色质可及性等调控信息，而直接整合这些异质模态常因统计结构差异导致表示坍缩。为此提出自监督多模态融合框架，将序列嵌入与局部及全局染色质可及性统一编码，借助全局归一化策略有效避免对齐退化。实验表明，该模型在染色质可及性峰检测上较仅序列基线取得四点六倍AUPRC提升，并在ClinVar、GTEx和PBMC等外部数据集上表现更优。该框架具备良好扩展性，为多模态DNA基础模型奠定重要方法基础。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有DNA基础模型仅使用序列难以全面反映调控信息，异质模态直接融合易导致表示坍缩。
method: 提出自监督多模态融合框架，结合序列嵌入与局部及全局染色质可及性，并通过全局归一化有效避免对齐坍缩。
result: 在染色质可及性峰检测中较仅序列基线AUPRC提升四点六倍，并在多个外部数据集上表现更好。
conclusion: 该框架能够方便地扩展到更多调控模态，为多模态DNA基础模型奠定了坚实的方法基础。
---

## 摘要
基于DNA序列预训练的基因组基础模型已在多种任务中取得强劲表现，但仅序列表示无法完全捕捉由额外DNA中心模态所反映的调控信息。现有的多模态基因组模型通常针对特定预测任务进行优化，而非用于学习跨下游分析可复用的嵌入表示。然而，直接融合异质性基因组模态颇具挑战，因为稀疏的峰状调控信号与密集的序列表示具有显著不同的统计结构，使得朴素的多模态对齐容易陷入退化的近零解。我们提出一种自监督的DNA中心多模态基础模型来解决这一差距，将DNA序列嵌入与局部及全局染色质可及性整合到共享的多模态编码器中，以生成可复用的窗口级嵌入，既支持预训练期间的掩码重建，也支持下游预测任务。我们诊断了这种异质性模态对齐失败，并表明全局归一化能显著缓解坍缩，从而实现跨模态的有效联合学习。所得嵌入提升了多项调控功能的下游评估，包括调控活性预测、调控信号排序和染色质可及性峰检测，在峰检测中相比仅DNA基线实现了4.6倍的AUPRC提升，并在ClinVar、GTEx eQTL和PBMC caQTL数据集上进一步改善了外部验证。该框架可扩展至更多调控模态，为多模态DNA基础模型提供了方法论基础。

## Abstract
Genomic foundation models pretrained on DNA sequence have achieved strong performance across a range of tasks, but sequence-only representations cannot fully capture regulatory information reflected by additional DNA-centric modalities. Existing multimodal genomic models are often optimized for specific prediction tasks rather than for learning reusable embeddings shared across downstream analyses. However, directly fusing heterogeneous genomic modalities is challenging because sparse, peak-shaped regulatory signals and dense sequence representations have markedly different statistical structures, making naive multimodal alignment prone to degenerate near-zero solutions. We present a self-supervised DNA-centric multimodal foundation model that addresses this gap, integrating DNA sequence embeddings with local and global chromatin accessibility in a shared multimodal encoder to produce reusable window-level embeddings that support both masked reconstruction during pre-training and downstream prediction tasks. We diagnose this heterogeneous-modality alignment failure and show that global normalization substantially alleviates collapse, enabling effective joint learning across modalities. The resulting embeddings improve multiple downstream evaluations of regulatory function, including regulatory activity prediction, regulatory signal ranking and chromatin accessibility peak detection, achieving a 4.6-fold AUPRC improvement over the DNA-only baseline in peak detection, and further improving external validation on ClinVar, GTEx eQTL and PBMC caQTL datasets. The framework is extensible to additional regulatory modalities, providing a methodological basis for multimodal DNA foundation models.