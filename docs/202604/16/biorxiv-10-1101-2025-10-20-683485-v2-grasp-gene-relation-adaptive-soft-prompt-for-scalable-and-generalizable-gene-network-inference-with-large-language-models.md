---
title: "GRASP: Gene-relation adaptive soft prompt for scalable and generalizable gene network inference with large language models"
title_zh: GRASP：基于大语言模型的可扩展且泛化基因网络推理的基因关系自适应软提示
authors: "Feng, Y., Deng, K., Guan, Y."
date: 2026-04-14
pdf: "https://www.biorxiv.org/content/10.1101/2025.10.20.683485v2.full.pdf"
tags: ["query:med-ai"]
score: 8.0
evidence: 大语言模型用于基因网络推理与生物知识整合
tldr: 基因网络（GN）推理对理解细胞功能至关重要，但现有方法受限于特定背景且大语言模型（LLM）推理对提示词敏感。本文提出GRASP框架，通过三个虚拟标记实现参数高效的软提示学习。该方法结合基因特异性和关系感知组件，将生物学背景映射为紧凑提示，在多种GN推理任务中表现优异，能有效识别未标注的生物关系，为基于LLM的基因网络推理提供了可扩展且通用的解决方案。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2025-10-20-683485-v2/fig-001.webp\", \"caption\": \"Figure 1. Framework overview. (A) Domain-specific continual pretraining. Approximately 6.3 million gene-related articles were curated from PubMed. Titles and abstracts were extracted to form a gene-focused corpus for continual pretraining. (B) Baseline methods. Few-shot inference relies on\", \"page\": 11, \"index\": 1, \"width\": 848, \"height\": 956}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2025-10-20-683485-v2/fig-002.webp\", \"caption\": \"Figure 4. Comparative performance on the kinase-substrate relationship inference. (A)\", \"page\": 14, \"index\": 2, \"width\": 840, \"height\": 545}]"
motivation: 现有的基因网络推理方法缺乏通用性，且大语言模型在处理此类任务时对提示词设计高度敏感。
method: 提出GRASP框架，利用分解的基因特异性和关系感知组件，通过三个可训练的虚拟标记生成自适应软提示。
result: GRASP在多项基因网络推理任务中优于传统提示策略，并能从合成负样本中有效恢复未标注的真实生物相互作用。
conclusion: GRASP为利用大语言模型进行大规模、通用的基因网络推理提供了一种高效且稳健的参数微调新范式。
---

## 摘要
基因网络 (GNs) 编码了多种分子关系，是解释细胞功能和疾病的核心。相互作用类型的异质性导致了专门针对特定网络背景的计算方法。大语言模型 (LLMs) 通过利用大规模文本语料库中的生物学知识，提供了一种统一的、基于语言的基因网络推理范式，但其有效性仍对提示词设计较为敏感。在此，我们提出了基因关系自适应软提示 (GRASP)，这是一个参数高效且可训练的框架，仅通过三个虚拟标记即可实现针对每对基因推理的条件化处理。通过使用分解的基因特异性和关系感知组件，GRASP 学习将每对基因的生物学背景映射为紧凑的软提示，从而结合了基因对特异性信号与共享的相互作用模式。在多种基因网络推理任务中，GRASP 的表现始终优于其他提示策略。它还展现出更强的从合成负集中恢复未标注相互作用的能力，表明其具有识别现有数据库之外具有生物学意义的关系的潜力。总之，这些结果确立了 GRASP 作为一种用于基于大语言模型的基因网络推理的可扩展且泛化性强的提示框架。

## Abstract
Gene networks (GNs) encode diverse molecular relationships and are central to interpreting cellular function and disease. The heterogeneity of interaction types has led to computational methods specialized for particular network contexts. Large language models (LLMs) offer a unified, language-based formulation of GN inference by leveraging biological knowledge from large-scale text corpora, yet their effectiveness remains sensitive to prompt design. Here, we introduce Gene-Relation Adaptive Soft Prompt (GRASP), a parameter-efficient and trainable framework that conditions inference on each gene pair through only three virtual tokens. Using factorized gene-specific and relation-aware components, GRASP learns to map each pair's biological context into compact soft prompts that combine pair-specific signals with shared interaction patterns. Across diverse GN inference tasks, GRASP consistently outperforms alternative prompting strategies. It also shows a stronger ability to recover unannotated interactions from synthetic negative sets, suggesting its capacity to identify biologically meaningful relationships beyond existing databases. Together, these results establish GRASP as a scalable and generalizable prompting framework for LLM-based GN inference.