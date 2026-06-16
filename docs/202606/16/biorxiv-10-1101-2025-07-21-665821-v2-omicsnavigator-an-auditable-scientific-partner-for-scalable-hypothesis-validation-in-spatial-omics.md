---
title: "OmicsNavigator: An auditable scientific partner for scalable hypothesis validation in spatial omics"
title_zh: OmicsNavigator：用于空间组学中可扩展假设验证的可审计科学伙伴
authors: "Li, Y., Vakharia, N., Liang, W., Mayer, A. T., Luo, R., Trevino, A. E., Wu, Z."
date: 2026-06-14
pdf: "https://www.biorxiv.org/content/10.1101/2025.07.21.665821v2.full.pdf"
tags: ["query:med-ai"]
score: 6.0
evidence: 基于大语言模型的空间组学假设验证系统，涉及大规模基因组模型和医学大语言模型
tldr: 空间组学数据转化可验证生物学发现是研究瓶颈。OmicsNavigator基于大语言模型，自主探索多模态空间组学数据，进行知识引导的结构注释。通过将高维数据转为文本，实现组织生物标志物零样本语义检索和患者疾病图谱重建。系统内置预注册审计假设验证引擎，在多种病理数据中生成基于证据的人可读洞见。
source: biorxiv
selection_source: fresh_fetch
motivation: 空间组学高维数据难以直接转化为可验证的生物学发现，亟需可扩展、可解释的分析工具。
method: 构建基于大语言模型的自主系统，将多模态空间组学数据转换为文本解释，实现零样本检索和假设验证。
result: 在糖尿病肾病、肾移植排斥、COVID-19肺病理数据中成功生成证据充分、人可理解的生物学洞见。
conclusion: OmicsNavigator提供可扩展、可解释、模态无关的空间组学分析方案，加速空间生物学发现。
---

## 摘要
将高维、空间分辨的分子数据集转化为可检验的生物学发现仍是一个主要的研究瓶颈。在此，我们提出OmicsNavigator，一个基于自主大语言模型的系统，用于空间组学数据的端到端数据探索和假设验证。OmicsNavigator直接对空间组学数据（包括视觉和分子特征）的多模态输入进行推理，以执行空间结构的知识引导注释。我们展示，通过将高维数据转化为文本解释，OmicsNavigator能够实现组织生物标志物的零样本语义检索，并从原始组学观测中重建患者级别的疾病图谱。此外，OmicsNavigator配备了一个由预注册、人工审核蓝图控制的目标假设验证引擎。通过在涵盖多种病理条件（包括糖尿病肾病、肾移植排斥和COVID-19肺部病理）的数据集上验证该系统，我们证明OmicsNavigator能从空间组学数据生成基于证据、人类可读的见解，具有加速空间生物学发现的潜力。OmicsNavigator为空间组学分析提供了可扩展、可解释且与模态无关的解决方案。

## Abstract
Translating high-dimensional, spatially resolved molecular datasets into testable biological findings remains a major research bottleneck. Here, we present OmicsNavigator, an autonomous large language model-powered system for end-to-end data exploration and hypothesis validation on spatial omics data. OmicsNavigator reasons directly over the multi-modal inputs of spatial omics data, including visual and molecular signatures, to perform knowledge-guided annotation of spatial structures. We show that by transforming high-dimensional data into textual interpretations, OmicsNavigator enables zero-shot semantic retrieval of tissue biomarkers and the reconstruction of patient-level disease profiles from raw omics observations. Furthermore, OmicsNavigator features an objective hypothesis validation engine governed by pre-registered, human-audited blueprints. By validating the system across datasets spanning diverse pathological conditions including diabetic kidney disease, kidney transplant rejection, and COVID-19 pulmonary pathology, we demonstrate that OmicsNavigator generates evidence-based, human-readable insights from spatial omics data, with potential to accelerate spatial biology discoveries.OmicsNavigator offers a scalable, interpretable, and modality-agnostic solution for spatial omics analysis.