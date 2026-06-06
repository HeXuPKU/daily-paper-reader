---
title: Bimodal masked language modeling for bulk RNA-seq and DNA methylation representation learning
title_zh: 基于双模态掩码语言建模的大规模RNA-seq和DNA甲基化表示学习
authors: "Gelard, M., Benkirane, H., Pierrot, T., Richard, G., Cournede, P.-H."
date: 2026-05-29
pdf: "https://www.biorxiv.org/content/10.1101/2025.06.25.661237v2.full.pdf"
tags: ["query:med-ai"]
score: 7.0
evidence: RNA-seq与DNA甲基化的双模态掩码语言模型，贡献于大规模基因组模型
tldr: 肿瘤学家依赖多模态数据建模疾病，但转录组和表观遗传数据的高维整合存在挑战。本文提出双模态掩码语言模型，联合学习RNA-seq与DNA甲基化表示，通过轻量架构降低内存占用。微调后的癌症分类和生存模型性能达到领先水平，且能容忍缺失模态，适用于临床场景。
source: biorxiv
selection_source: fresh_fetch
motivation: 整合高维转录组和DNA甲基化数据用于临床建模面临挑战，现有方法难以处理长序列和缺失模态。
method: 采用掩码语言建模自监督学习，设计减少内存占用的双模态Transformer架构，联合嵌入RNA-seq与甲基化数据。
result: 得到的双模态嵌入在癌症类型分类和生存预测上达到领先性能，且对缺失模态具有鲁棒性。
conclusion: 该双模态表示学习框架有效融合异质数据，提升了临床模型的准确性和实用性。
---

## 摘要
肿瘤学家越来越依赖多种模态来模拟疾病的复杂性。在此背景下，转录组和表观遗传数据已被证明特别有用，并在临床应用中发挥着越来越重要的作用。然而，将它们整合到多模态模型中仍然是一个挑战，尤其是考虑到它们的高维性。在这项工作中，我们提出了一种新颖的双模态模型，该模型利用掩码语言建模的自监督学习共同学习批量RNA-seq和DNA甲基化的表示。我们实现了一种架构，减少了通常纯基于Transformer模型在处理长序列时的内存占用。我们证明了所获得的双模态嵌入可用于微调癌症类型分类和生存模型，与单模态模型相比，这些模型实现了最先进的性能。此外，我们引入了一个鲁棒的学习框架，即使在缺失模态的情况下也能保持下游任务的性能，从而增强了模型在实际临床环境中的适用性。

## Abstract
Oncologists are increasingly relying on multiple modalities to model the complexity of diseases. Within this landscape, transcriptomic and epigenetic data have proven to be particularly instrumental and play an increasingly vital role in clinical applications. However, their integration into multimodal models remains a challenge, especially considering their high dimensionality. In this work, we present a novel bimodal model that jointly learns representations of bulk RNA-seq and DNA methylation leveraging self-supervision from masked language modeling. We implement an architecture that reduces the memory footprint usually attributed to purely transformer-based models when dealing with long sequences. We demonstrate that the obtained bimodal embeddings can be used to fine-tune cancer-type classification and survival models that achieve state-of-the-art performance compared to unimodal models. Furthermore, we introduce a robust learning framework that maintains downstream task performance despite missing modalities, enhancing the models applicability in real-world clinical settings.