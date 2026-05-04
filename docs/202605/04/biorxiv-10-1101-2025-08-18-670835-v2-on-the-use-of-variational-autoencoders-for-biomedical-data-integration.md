---
title: On the use of variational autoencoders for biomedical data integration
title_zh: 论变分自编码器在生物医学数据集成中的应用
authors: "Pielies Avelli, M., Hernandez Medina, R., Webel, H. E., Rasmussen, S."
date: 2026-04-30
pdf: "https://www.biorxiv.org/content/10.1101/2025.08.18.670835v2.full.pdf"
tags: ["query:med-ai"]
score: 7.0
evidence: 基于变分自编码器的多模态生物医学数据整合框架
tldr: 本研究探讨了变分自编码器（VAE）在整合多样化生物医学数据中的应用。基于此前开发的MOVE框架，作者深入分析了多模态VAE的内部机制，并扩展了该框架以处理连续变量的扰动。通过引入新的关联捕捉方法和合成数据集基准测试，研究展示了如何利用计算机模拟扰动来识别变量间的潜在联系。最终在炎症性肠病和基因敲除数据集上的应用证明了该方法在揭示复杂生物医学关联方面的有效性。
source: biorxiv
selection_source: fresh_fetch
motivation: 旨在利用变分自编码器更有效地整合多模态生物医学数据，并深入理解变量间的复杂关联。
method: 扩展了MOVE框架以支持连续变量扰动，并提出一种新方法来捕捉变量间的关联，同时利用合成数据进行基准测试。
result: 改进后的框架在合成数据上准确识别了预设关联，并在炎症性肠病及基因敲除的真实场景中展示了其发现潜在生物学联系的能力。
conclusion: VAE框架是生物医学数据整合和关联发现的强大工具，通过模拟扰动可为复杂疾病研究提供重要见解。
---

## 摘要
变分自编码器（VAEs）是一种广泛使用的框架，用于集成多种生物医学数据模态，创建能够捕捉数据集底层结构的表示，并获取关于变量间关系的见解。在本文中，我们从经验角度描述了在我们之前开发的基于 VAE 的框架 MOVE 中是如何实现这一目标的，为生物医学背景下多模态 VAE 的内部运行机制提供了一个直观的视角。我们探讨了模型的涌现动力学如何塑造其性能，以及如何利用计算机模拟（in silico）扰动来识别变量之间的潜在关联。为此，我们扩展了框架以处理连续变量的扰动，引入了一种能更好捕捉变量间关联的新方法，并创建了合成数据集，以便根据明确定义的基准真值（ground truth）关联对所提方法进行基准测试。最后，我们在真实的生物医学场景中展示了我们的发现，即炎症性肠病的多模态数据集以及包含 K562 和 RPE1 细胞基因敲低的数据集。

## Abstract
Variational Autoencoders (VAEs) are a widely used framework to integrate diverse biomedical data modalities, create representations that capture the underlying structure of the datasets, and obtain insights about the relations between variables. Here we describe how this is achieved from an empirical point of view in our previously developed VAE-based framework MOVE, providing an intuitive perspective on the inner workings of multimodal VAEs in biomedical contexts. We explore how the models' emerging dynamics shape their performance and how in silico perturbations can be leveraged to identify potential associations between variables. To do that, we extend our framework to handle perturbations of continuous variables, introduce a new approach to better capture associations between them, and create synthetic datasets to benchmark the proposed methods against well-defined ground truth associations. We finally showcase our findings in real biomedical scenarios, namely a multimodal dataset of inflammatory bowel disease and a dataset containing genetic knockdowns in K562 and RPE1 cells.