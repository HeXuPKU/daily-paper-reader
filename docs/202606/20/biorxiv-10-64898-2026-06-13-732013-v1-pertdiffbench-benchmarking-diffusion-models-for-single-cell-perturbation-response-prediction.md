---
title: "PertDiffBench: Benchmarking Diffusion Models for Single-Cell Perturbation Response Prediction"
title_zh: PertDiffBench：用于单细胞扰动响应预测的扩散模型基准测试
authors: "Song, Z., Xiang, Y., Jin, W., Li, J., Sun, C., Xie, L."
date: 2026-06-13
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.13.732013v1.full.pdf"
tags: ["query:med-ai"]
score: 7.0
evidence: 扩散模型基准测试用于单细胞扰动预测，符合虚拟细胞/基因组大模型
tldr: 单细胞转录组扰动响应预测中，扩散模型的评估缺乏标准化，导致其实际优势不明确。为此，我们提出PertDiffBench基准，涵盖标准预测、泛化测试和压力测试。结果发现扩散模型无一致优势：scGen在常见任务中强劲，scDiffusion在泛化中表现较好，而时间插补中简单DDPM更优。性能强烈依赖于任务设计和输入表示，该基准为系统评估提供了实用框架。
source: biorxiv
selection_source: fresh_fetch
motivation: 缺乏标准化基准来评估扩散模型在单细胞扰动预测中的实际优势。
method: 构建PertDiffBench，包含标准预测、泛化测试和压力测试等多组评估。
result: 扩散模型无一致优势，scGen和简单DDPM在特定任务中更优，性能依赖任务设计。
conclusion: 扩散模型性能受任务和表示选择显著影响，PertDiffBench提供系统评估框架。
---

## 摘要
扩散模型越来越多地被用于预测扰动后的转录响应，但它们是否优于更简单的生成模型和基于表征的基线模型尚不清楚。现有评估通常不区分模型架构、输入表示、生物学背景和指标选择的影响，因此难以确定扩散方法在哪些场景下有用。本文提出PertDiffBench，一个基于扩散的转录组扰动预测标准化基准，涵盖单细胞和批量RNA-seq数据集。PertDiffBench在三个互补的评估设置中评估基于扩散的模型：已知单细胞背景和批量扰动条件下的标准预测、泛化到未见过的细胞类型、物种、药物和中间时间点，以及对特征维度、输入表示、噪声类型和基因排序的鲁棒性测试。在这些设置中，扩散模型并未表现出一致的优势。scGen在常见预测任务中仍是一个强大的基线，而scDiffusion在多个泛化设置中是最具竞争力的扩散方法。时间插值显示出不同的模式，一个直接在表达空间操作的简单DDPM优于更专门的模型。鲁棒性测试表明性能依赖于模型，并对特征维度、编码器选择、噪声类型和基因排序敏感。预训练编码器并未持续提升性能，经典的scVI表示在已知条件和未见细胞类型设置中略优于STATE。这些结果表明，扩散模型在扰动响应预测中的性能强烈依赖于任务设计和表示选择。PertDiffBench提供了一个实用框架，用于在生物学多样性和鲁棒性测试条件下评估这些模型。

## Abstract
Diffusion models are increasingly used to predict transcriptional responses to perturbations, but whether they improve on simpler generative and representation-based baselines remains unclear. Existing evaluations often do not separate the effects of model architecture, input representation, biological context and metric choice, making it difficult to determine where diffusion-based methods are useful. Here we introduce PertDiffBench, a standardized benchmark for diffusion-based transcriptomic perturbation prediction across single-cell and bulk RNA-seq datasets. PertDiffBench evaluates diffusion-based models across three complementary evaluation settings: standard prediction in known single-cell contexts and bulk perturbation conditions, generalization to unseen cell types, species, drugs and intermediate time points, and stress tests of feature dimensionality, input representation, noise type and gene ordering. Across these settings, diffusion models did not show a consistent advantage. scGen remained a strong baseline in common prediction tasks, whereas scDiffusion was the most competitive diffusion-based method in several generalization settings. Temporal imputation showed a different pattern, with a simple DDPM operating directly in expression space outperforming more specialized models. Stress tests showed that performance was model dependent and sensitive to feature dimensionality, encoder choice, noise type and gene ordering. Pretrained encoders did not consistently improve performance, with the classical scVI representation slightly exceeding STATE in seen-condition and unseen-cell-type settings. These results indicate that diffusion-model performance in perturbation response prediction depends strongly on task design and representation choice. PertDiffBench provides a practical framework for evaluating these models under biologically varied and stress-tested conditions.