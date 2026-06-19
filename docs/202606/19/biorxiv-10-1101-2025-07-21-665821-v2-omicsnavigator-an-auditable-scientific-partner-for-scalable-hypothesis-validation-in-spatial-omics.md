---
title: "OmicsNavigator: An auditable scientific partner for scalable hypothesis validation in spatial omics"
title_zh: OmicsNavigator：用于空间组学可扩展假设验证的可审计科学伙伴
authors: "Li, Y., Vakharia, N., Liang, W., Mayer, A. T., Luo, R., Trevino, A. E., Wu, Z."
date: 2026-06-14
pdf: "https://www.biorxiv.org/content/10.1101/2025.07.21.665821v2.full.pdf"
tags: ["query:med-ai"]
score: 7.0
evidence: 利用大语言模型进行空间组学数据假设验证
tldr: 空间组学数据的高维特性阻碍了生物学发现的转化。OmicsNavigator利用大语言模型直接推理多模态输入，实现知识引导的空间结构注释和零样本生物标志物检索。该系统通过预注册蓝图的假设验证引擎，在糖尿病肾病、肾移植排斥和COVID-19肺病理数据上生成可解释的洞察，加速空间生物学发现。
source: biorxiv
selection_source: fresh_fetch
motivation: 高维空间组学数据转化为可验证生物学假设存在瓶颈，亟需自动化推理系统。
method: 基于大语言模型，融合视觉与分子特征，通过文本化解释执行知识驱动注释和客观验证。
result: 系统准确识别组织标志物并重建疾病概况，在多种病理条件下生成证据充分的人类可读结论。
conclusion: OmicsNavigator实现了空间组学数据的可审计、可扩展假设验证，有望推动精准医学研究。
---

## 摘要
将高维、空间分辨的分子数据集转化为可检验的生物学发现仍是一个主要研究瓶颈。这里，我们提出OmicsNavigator，一个基于自主大型语言模型的系统，用于空间组学数据的端到端数据探索和假设验证。OmicsNavigator直接对空间组学数据的多模态输入（包括视觉和分子特征）进行推理，执行空间结构的知识引导注释。我们表明，通过将高维数据转换为文本解释，OmicsNavigator能够实现组织生物标志物的零样本语义检索，并从原始组学观测重建患者水平的疾病特征。此外，OmicsNavigator具有一个由预先注册、人工审计蓝图控制的客观假设验证引擎。通过在不同病理条件（包括糖尿病肾病、肾移植排斥反应和COVID-19肺部病理）的数据集上验证系统，我们证明OmicsNavigator从空间组学数据中生成了基于证据、人类可读的见解，有潜力加速空间生物学发现。

## Abstract
Translating high-dimensional, spatially resolved molecular datasets into testable biological findings remains a major research bottleneck. Here, we present Omic-sNavigator, an autonomous large language model-powered system for end-to-end data exploration and hypothesis validation on spatial omics data. OmicsNaviga-tor reasons directly over the multi-modal inputs of spatial omics data, including visual and molecular signatures, to perform knowledge-guided annotation of spatial structures. We show that by transforming high-dimensional data into textual interpretations, OmicsNavigator enables zero-shot semantic retrieval of tissue biomarkers and the reconstruction of patient-level disease profiles from raw omics observations. Furthermore, OmicsNavigator features an objective hypothesis validation engine governed by pre-registered, human-audited blueprints. By validating the system across datasets spanning diverse pathological conditions including diabetic kidney disease, kidney transplant rejection, and COVID-19 pulmonary pathology, we demonstrate that OmicsNavigator generates evidence-based, human-readable insights from spatial omics data, with potential to accelerate spatial biology discoveries.