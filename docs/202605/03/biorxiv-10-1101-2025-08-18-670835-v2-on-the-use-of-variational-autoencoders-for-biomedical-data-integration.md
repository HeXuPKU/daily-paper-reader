---
title: On the use of variational autoencoders for biomedical data integration
title_zh: 关于变分自编码器在生物医学数据整合中的应用
authors: "Pielies Avelli, M., Hernandez Medina, R., Webel, H. E., Rasmussen, S."
date: 2026-04-30
pdf: "https://www.biorxiv.org/content/10.1101/2025.08.18.670835v2.full.pdf"
tags: ["query:med-ai"]
score: 7.0
evidence: 基于VAE的框架，用于整合多种生物医学数据模态
tldr: 本研究探讨了变分自编码器（VAE）在整合多样化生物医学数据中的应用，重点介绍了MOVE框架。研究者通过扩展该框架以处理连续变量的扰动，并引入新方法来识别变量间的潜在关联。通过在合成数据集和真实生物医学场景（如炎症性肠病和基因敲除数据）中的验证，展示了该方法在捕捉复杂数据结构和发现变量间关系方面的有效性。
source: biorxiv
selection_source: fresh_fetch
motivation: 旨在利用VAE框架更有效地整合多模态生物医学数据，并深入理解变量间的复杂关联。
method: 扩展了MOVE框架以支持连续变量的计算机模拟扰动，并开发了新的关联识别方法。
result: 在合成基准测试和真实世界的炎症性肠病及基因敲除数据集中成功识别了关键的变量关联。
conclusion: 改进后的VAE框架为生物医学数据的多模态整合和潜在生物学机制的发现提供了强有力的工具。
---

## 摘要
变分自编码器（VAEs）是一种广泛使用的框架，用于整合多种生物医学数据模态，构建能够捕捉数据集底层结构的表示，并获取变量间关系的见解。本文从经验角度描述了在我们此前开发的基于 VAE 的框架 MOVE 中如何实现这一目标，为生物医学背景下多模态 VAE 的内部运作机制提供了直观视角。我们探讨了模型的涌现动力学如何影响其性能，以及如何利用计算机模拟（in silico）扰动来识别变量间的潜在关联。为此，我们扩展了框架以处理连续变量的扰动，引入了一种能更好捕捉变量间关联的新方法，并创建了合成数据集，以便根据明确的基准真值关联对所提方法进行基准测试。最后，我们在真实的生物医学场景中展示了研究结果，包括炎症性肠病的多模态数据集，以及包含 K562 和 RPE1 细胞基因敲低的数据集。

## Abstract
Variational Autoencoders (VAEs) are a widely used framework to integrate diverse biomedical data modalities, create representations that capture the underlying structure of the datasets, and obtain insights about the relations between variables. Here we describe how this is achieved from an empirical point of view in our previously developed VAE-based framework MOVE, providing an intuitive perspective on the inner workings of multimodal VAEs in biomedical contexts. We explore how the models' emerging dynamics shape their performance and how in silico perturbations can be leveraged to identify potential associations between variables. To do that, we extend our framework to handle perturbations of continuous variables, introduce a new approach to better capture associations between them, and create synthetic datasets to benchmark the proposed methods against well-defined ground truth associations. We finally showcase our findings in real biomedical scenarios, namely a multimodal dataset of inflammatory bowel disease and a dataset containing genetic knockdowns in K562 and RPE1 cells.