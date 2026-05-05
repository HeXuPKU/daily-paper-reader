---
title: A Multi-modal LLM-Knowledge Fusion Framework for Predicting Single-cell Genetic Perturbation Effects
title_zh: 一种用于预测单细胞基因扰动效应的多模态大语言模型-知识融合框架
authors: "LU, M., YOU, N., ZHANG, H., ZHENG, L., LI, B., JIANG, W., ZHANG, Y., SUN, H., ZHOU, Y."
date: 2026-04-28
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.24.720560v1.full.pdf"
tags: ["query:med-ai"]
score: 8.0
evidence: 多模态大语言模型与知识融合预测遗传扰动效应
tldr: 针对实验方法在基因扰动研究中的高成本和局限性，本文提出scPert框架。该框架基于Transformer架构，通过多模态融合大语言模型嵌入、结构化生物知识图谱和基因特定编码，实现了对单细胞转录组响应的高精度预测。scPert在单基因及组合扰动预测上表现优异，能揭示复杂的生物通路机制并识别潜在药物靶点，为构建“虚拟细胞”奠定了计算基础。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有的计算模型在处理复杂基因相互作用、生物可解释性及对未知基因的泛化能力方面存在不足。
method: 提出scPert框架，利用Transformer架构分层融合知识图谱表示、基础模型上下文嵌入和基因特定编码。
result: scPert在单基因和组合扰动预测性能上显著优于现有方法，并成功识别出42个癌症依赖基因中的关键治疗靶点。
conclusion: 该框架为虚拟细胞构建提供了强大的计算基础，并能有效加速药物靶点的发现过程。
---

## 摘要
理解细胞对基因扰动的响应是药物发现的基础，然而实验方法在覆盖范围和成本方面面临重大局限，阻碍了对细胞行为的全面映射。这促使了“虚拟细胞”的发展——即通过学习细胞状态与功能之间的关系，来预测不同背景下扰动后果的计算模型。然而，目前的计算方法在复杂基因相互作用中的准确性有限，生物学可解释性较差，且对未见基因的泛化能力不足，严重制约了虚拟细胞的能力。我们提出了 scPert，这是一个基于 Transformer 架构的多模态框架，它整合了大语言模型嵌入与结构化生物知识，用于预测单细胞对基因扰动的转录组响应。通过对知识图谱表示、基础模型的上下文嵌入以及基因特异性编码进行分层融合，scPert 在单基因和组合扰动预测方面均比现有方法取得了显著的性能提升。在癌症相关应用中，scPert 展示了揭示 p53 通路动力学和免疫检查点调节机制的能力。对 42 个癌症依赖基因的系统评估证明了 scPert 识别关键潜在治疗靶点的能力。我们的框架为虚拟细胞构建奠定了强大的计算基础，并加速了药物靶点的发现。

## Abstract
Understanding cellular responses to genetic perturbations is fundamental for drug discovery, yet experimental approaches face significant limitations in coverage and cost that prevent comprehensive mapping of cellular behavior. This has motivated the development of virtual cells--computational models that learn the relationship between cell state and function to predict the consequences of perturbations across diverse contexts. However, current computational methods suffer from limited accuracy in complex genetic interactions, poor biological interpretability, and inadequate generalization to unseen genes, severely constraining virtual cell capabilities. We present scPert, a multi-modal framework based on Transformer architecture that integrates large language model embeddings with structured biological knowledge to predict single-cell transcriptomic responses to genetic perturbations. Through hierarchical fusion of knowledge graph representations, contextual embeddings from foundation models, and gene-specific encodings, scPert achieves significant performance improvements in both single-gene and combinatorial perturbations over existing methods. In cancer-relevant applications, scPert demonstrates the capability to reveal p53 pathway dynamics and immune checkpoint regulatory mechanisms. Systematic evaluation on 42 cancer dependency genes demonstrates scPerts ability to identify critical potential therapeutic targets. Our framework establishes a powerful computational foundation for virtual cell construction and accelerates drug target discovery.