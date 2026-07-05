---
title: MORPH Predicts the Single-Cell Outcome of Genetic Perturbations Across Conditions and Data Modalities
title_zh: MORPH预测跨条件和数据模态的遗传扰动单细胞结果
authors: "He, C., Zhang, J., Dahleh, M. A., Uhler, C."
date: 2026-07-01
pdf: "https://www.biorxiv.org/content/10.1101/2025.06.27.661992v2.full.pdf"
tags: ["query:med-ai"]
score: 7.0
evidence: 使用变分自编码器和注意力机制预测基因扰动后的单细胞结果，与大规模基因组模型和虚拟细胞生成相关
tldr: 预测遗传扰动对单细胞的影响是计算生物学难题。MORPH结合差异变分自编码器和注意力机制，从转录组和成像数据学习细胞状态表示，可泛化预测未见扰动、组合扰动及新细胞环境下的反应。该方法还能推断基因调控网络并指导实验设计。MORPH为高效探索扰动空间提供了灵活工具，有助于基础与治疗研究。
source: biorxiv
selection_source: fresh_fetch
motivation: 测量所有基因扰动及其组合在实验上难以实现，亟需能跨数据类型泛化的预测模型。
method: MORPH采用基于差异的变分自编码器与注意力机制，学习细胞状态表示并预测扰动响应。
result: 支持单细胞转录组和成像输出，泛化到未见扰动、组合扰动及新细胞环境，推断基因相互作用网络。
conclusion: MORPH作为灵活工具，可优化扰动实验设计，高效探索扰动空间以理解细胞程序。
---

## 摘要
对细胞响应遗传扰动的建模是计算生物学中的一个重大挑战。测量所有基因扰动及其在细胞类型和条件中的组合在实验上具有挑战性，这突显了需要能够跨数据类型泛化的预测模型来支持这一任务。这里我们提出MORPH，一个用于预测扰动变化响应的模块化框架。MORPH结合了基于差异的变分自编码器和注意力机制，以预测细胞对未见扰动的响应。它支持单细胞转录组学和成像输出，并能泛化到未见扰动、扰动组合以及新细胞环境中的扰动。基于注意力的框架能够推断基因相互作用和调控网络，而学习到的基因嵌入可以指导信息性扰动的设计，如在两个应用中所展示的。总体而言，MORPH是一个用于优化扰动实验的灵活工具，能够高效探索扰动空间，以增进对细胞程序的理解，为基础研究和治疗应用提供支持。

## Abstract
Modeling cellular responses to genetic perturbations is a significant challenge in computational biology. Measuring all gene perturbations and their combinations across cell types and conditions is experimentally challenging, highlighting the need for predictive models that generalize across data types to support this task. Here we present MORPH, a MOdular framework for predicting Responses to Perturbational cHanges. MORPH combines a discrepancy-based variational autoencoder with an attention mechanism to predict cellular responses to unseen perturbations. It supports both single-cell transcriptomics and imaging outputs and can generalize to unseen perturbations, combinations of perturbations, and perturbations in new cellular contexts. The attention-based framework enables inference of gene interactions and regulatory networks, while the learned gene embeddings can guide the design of informative perturbations, as demonstrated in two applications. Overall, MORPH is a flexible tool for optimizing perturbation experiments, enabling efficient exploration of the perturbation space to advance understanding of cellular programs for fundamental research and therapeutic applications.