---
title: MORPH Predicts the Single-Cell Outcome of Genetic Perturbations Across Conditions and Data Modalities
title_zh: MORPH预测遗传扰动在不同条件和数据模态下的单细胞结果
authors: "He, C., Zhang, J., Dahleh, M. A., Uhler, C."
date: 2026-07-01
pdf: "https://www.biorxiv.org/content/10.1101/2025.06.27.661992v2.full.pdf"
tags: ["query:med-ai"]
score: 7.0
evidence: 使用深度学习预测遗传扰动的单细胞结果，与虚拟细胞模型和基因组模型相关
tldr: 基因扰动建模面临实验难以覆盖所有组合的挑战。MORPH框架整合差异变分自编码器与注意力机制，能够预测未见扰动、扰动组合及新细胞上下文下的单细胞转录组和成像响应。该模型不仅泛化到多种数据模态，还能推断基因交互网络。其学习到的基因嵌入可指导高效扰动设计，为理解细胞程序及治疗应用提供优化实验工具。
source: biorxiv
selection_source: fresh_fetch
motivation: 预测细胞对遗传扰动的响应是计算生物学难题，现有方法难以泛化到未见条件及不同数据模态。
method: 提出MORPH，结合差异变分自编码器与注意力机制，预测单细胞转录组与成像输出，并推断基因调控网络。
result: 模型可预测未见扰动及其组合，在不同细胞上下文中泛化，并支持多模态数据输出。
conclusion: MORPH为优化扰动实验提供灵活框架，加速对细胞程序的基础研究与治疗应用探索。
---

## 摘要
模拟细胞对遗传扰动的反应是计算生物学中的一个重大挑战。测量所有基因扰动及其在细胞类型和条件下的组合在实验上具有挑战性，这凸显了对能够跨数据类型泛化的预测模型的需求，以支持这一任务。在此，我们提出MORPH——一种用于预测扰动变化反应的模块化框架。MORPH结合了基于差异的变分自编码器和注意力机制，以预测细胞对未见扰动的反应。它支持单细胞转录组学和成像输出，并能泛化到未见扰动、扰动组合以及新细胞环境中的扰动。基于注意力的框架能够推断基因相互作用和调控网络，而学习到的基因嵌入可以指导有信息量的扰动设计，这在两个应用中得到了证明。总体而言，MORPH是一种优化扰动实验的灵活工具，能够有效探索扰动空间，以增进对细胞程序的理解，为基础研究和治疗应用提供支持。

## Abstract
Modeling cellular responses to genetic perturbations is a significant challenge in computational biology. Measuring all gene perturbations and their combinations across cell types and conditions is experimentally challenging, highlighting the need for predictive models that generalize across data types to support this task. Here we present MORPH, a MOdular framework for predicting Responses to Perturbational cHanges. MORPH combines a discrepancy-based variational autoencoder with an attention mechanism to predict cellular responses to unseen perturbations. It supports both single-cell transcriptomics and imaging outputs and can generalize to unseen perturbations, combinations of perturbations, and perturbations in new cellular contexts. The attention-based framework enables inference of gene interactions and regulatory networks, while the learned gene embeddings can guide the design of informative perturbations, as demonstrated in two applications. Overall, MORPH is a flexible tool for optimizing perturbation experiments, enabling efficient exploration of the perturbation space to advance understanding of cellular programs for fundamental research and therapeutic applications.