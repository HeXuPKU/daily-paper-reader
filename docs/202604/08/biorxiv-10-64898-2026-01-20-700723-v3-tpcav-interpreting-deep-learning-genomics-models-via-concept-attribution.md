---
title: "TPCAV: Interpreting deep learning genomics models via concept attribution"
title_zh: TPCAV：通过概念归因解释基因组学深度学习模型
authors: "Yang, J., Mahony, S."
date: 2026-04-08
pdf: "https://www.biorxiv.org/content/10.64898/2026.01.20.700723v3.full.pdf"
tags: ["query:gwas"]
score: 8.0
evidence: 通过概念归因解释基因组学深度学习模型
tldr: 针对基因组学深度学习模型解释性受限于独热编码输入的问题，本文提出了TPCAV方法。该方法通过改进概念激活向量（TCAV），引入PCA去相关变换处理冗余特征，实现了对DNA序列、染色质状态及重复序列等多种基因组特征的全局解释。TPCAV不仅能提取特定概念的归因图，还适用于分词基础模型，为理解复杂生物调控机制提供了灵活且鲁棒的工具。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-01-20-700723-v3/fig-001.webp\", \"caption\": \"Figure 4: Concept specific attribution map reveals differential usage of concepts across prediction heads in BPNet. a) Top 10 motif concepts identified in the last shared convolutional layer by all prediction heads. b) CAV cosine similarity heatmap of top 30 motif concepts (F-score > 0.9) in BPNet. c) Log TPCAV scores of top 30 motif concepts (F-score > 0.9) across all prediction tasks, bar color indicates whether a concept is positive (red) or negative (blue) influence.\", \"page\": 15, \"index\": 1, \"width\": 950, \"height\": 1152}]"
motivation: 现有的基因组学模型解释方法多局限于独热编码输入，难以评估染色质状态或重复序列等更广泛基因组特征的影响。
method: 提出TPCAV方法，通过在TCAV基础上引入PCA投影来消除嵌入特征的相关性，并开发了提取概念特定输入归因图的策略。
result: 实验证明TPCAV在转录因子结合预测中表现与TF-MoDISco相当，并能有效解释重复元件、染色质状态及基础模型学习到的特征。
conclusion: TPCAV是一种灵活且鲁棒的解释工具，能够跨多种输入表示和任务识别关键生物概念，是对现有解释技术的有力补充。
---

## 摘要
解释基因组学深度学习模型仍然具有挑战性。现有的特征归因方法很大程度上局限于 one-hot 编码的 DNA 输入，因此无法评估更通用的基因组特征（如染色质状态或基因组重复序列）的影响。概念归因方法提供了一种与输入无关的全局解释框架，但尚未系统地应用于解释基因组学中的神经网络应用。我们通过改进“基于概念激活向量的测试”（TCAV）方法，首次将概念归因应用于解释基因组学深度学习模型。我们通过引入基于 PCA 的去相关变换来改进原始 TCAV 方法，以解决基因组学深度学习模型中常见的相关且冗余的嵌入特征，从而形成了“基于 PCA 投影概念激活向量的测试”（TPCAV）方法。我们还引入了一种提取特定概念输入归因图的策略。我们通过在涵盖多种输入表示和预测任务的多样化基因组模型集中解释有影响力的生物学概念，评估了我们的方法。我们证明，在基于 one-hot 编码 DNA 的转录因子结合预测模型上，TPCAV 提供了与 TF-MoDISco 相当的 motif 特征解释。TPCAV 还能对更通用的生物学概念（如重复元件和染色质状态注释）如何对预测做出贡献进行稳健的解释性分析。TPCAV 具有独特的泛化能力，可以解释由分词化基础模型以及将染色质信号作为输入的模型所学习到的特征。我们进一步展示了 TPCAV 可以识别与特定概念相关的代表性区域，从而激发对不同调控机制的下游研究。TPCAV 为现有的模型解释技术提供了一个灵活且稳健的补充。

## Abstract
Interpreting genomics deep learning models remains challenging. Existing feature attribution methods are largely restricted to one-hot DNA inputs and therefore cannot assess the influence of more general genomic features such as chromatin states or genomic repeats. Concept attribution methods offer an input-agnostic global interpretation framework, yet they have not been systematically applied to interpret neural network applications in genomics. We present the first application of concept attribution to interpret genomics deep learning models by adapting the Testing with Concept Activation Vectors (TCAV) method. We improve upon the original TCAV method by incorporating a PCA-based decorrelation transformation to address correlated and redundant embedding features commonly observed in genomics deep learning models, resulting in the Testing with PCA-projected Concept Activation Vectors (TPCAV) approach. We also introduce a strategy for extracting concept-specific input attribution maps. We evaluate our approach by interpreting influential biological concepts across a diverse set of genomics models spanning multiple input representations and prediction tasks. We demonstrate that TPCAV provides comparable motif feature interpretation to TF-MoDISco on one-hot encoded DNA-based transcription factor binding prediction models. TPCAV also enables robust interpretive analysis of how more general biological concepts such as repetitive elements and chromatin state annotations contribute towards predictions. TPCAV uniquely generalizes to interpret features learned by tokenized foundation models as well as models incorporating chromatin signals as inputs. We further show that TPCAV can identify representative regions associated with specific concepts, motivating downstream investigation of distinct regulatory mechanisms. TPCAV provides a flexible and robust complement to existing model interpretation techniques.