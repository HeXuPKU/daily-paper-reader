---
title: Improving Causal Gene Identification Using Large Language Models
title_zh: 利用大语言模型改进致病基因识别
authors: "Ofer, D., Kaufman, H."
date: 2026-03-10
pdf: "https://www.biorxiv.org/content/10.64898/2026.03.08.710344v1.full.pdf"
tags: ["query:med-ai"]
score: 10.0
evidence: 大语言模型用于GWAS因果基因识别
tldr: 本研究针对全基因组关联分析（GWAS）中因果基因识别的难题，评估了大型语言模型（LLM）的应用潜力。通过在Qwen2.5模型中集成检索增强生成（RAG）技术和基因组距离信息，研究者在Open Targets基准数据集上显著提升了预测准确率。结果表明，结合结构化基因组特征与非结构化文本数据的混合方法能有效弥补传统启发式方法的不足，为自动化因果基因识别提供了新思路。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-08-710344-v1/fig-001.webp\", \"caption\": \"Figure 1: Comparison of Baseline vs. Distance-Based Prompts. Subfigure (a) uses a general chain-ofthought prompt and incorrectly selects CORIN. Subfigure (b) integrates sorted gene-distance information and highlights ATP10D as the true causal gene for sphingolipid levels. Final suffix of prompts enforcing json structure removed for clarity. Inputs detailed in V-A\", \"page\": 3, \"index\": 1, \"width\": 887, \"height\": 241}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-08-710344-v1/fig-002.webp\", \"caption\": \"Figure 2: Comparison of model performance. We compare the results of the small phi-4 model with those of the qwen2.5 model. Light blue indicates the use of medRAG and pink indicates a model without RAG. A triangle indicates the use of distances for analysis and a circle indicates a model without distance information. The gray dashed line indicates the performance of Shringarpure et al using GPT4o.\", \"page\": 4, \"index\": 2, \"width\": 713, \"height\": 563}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-08-710344-v1/fig-003.webp\", \"caption\": \"Figure 3: Mistake type distribution between (a) baseline model, and (b) with additional literature and genetic distance information. We note the difference in mistaken paralogs\", \"page\": 5, \"index\": 3, \"width\": 358, \"height\": 756}]"
motivation: 传统的基于距离的启发式方法在GWAS因果基因识别中效果有限，且现有大语言模型在知识表示和检索方面仍存在局限。
method: 研究采用Qwen2.5模型，通过集成RAG文献检索和基因组距离信息，在Open Targets基准数据集上进行因果基因识别评估。
result: 引入RAG和基因组距离信息后，模型F1分数分别提升至0.795和0.806，但两者结合使用时效果并未线性叠加。
conclusion: 结合结构化基因组特征与非结构化文献数据的混合方法，在提升因果基因识别准确性方面具有显著潜力。
---

## 摘要
全基因组关联研究（GWAS）已成功识别出大量与复杂性状和疾病相关的位点，但精准定位致病基因（causal genes）仍是一项重大挑战。由于连锁不平衡、基因相互作用和调控效应的存在，仅依赖简单的基于距离的启发式方法往往是不够的。大语言模型（LLMs）的最新进展展示了在自动化致病基因识别方面的潜力，但其有效性仍受限于知识表示和检索机制。本研究在先前研究的基础上，评估了 LLMs 在致病基因识别中的表现，重点关注通过检索增强生成（RAG）和整合基因组距离信息来提升性能。我们使用较小的模型 Qwen2.5 复现了先前的结果，并利用 Open Targets 的基准数据集评估了其预测准确性。在整合基于 RAG 的文献检索（F1 = 0.795）和基因距离信息（F1 = 0.806）后，性能得到了提升。然而，组合方法产生的收益递减，表明这些增强手段之间存在相互作用。错误分析显示，基因组距离特征通过强化已有的启发式规则改进了预测，而 RAG 增强了领域知识，但偶尔会导致语义偏差。这些发现强调了混合方法在利用结构化基因组特征和非结构化文本数据方面的潜力。

## Abstract
Genome-Wide Association Studies (GWAS) have successfully identified numerous loci associated with complex traits and diseases, yet pinpointing causal genes remains a significant challenge. The reliance on simple proximity-based heuristics is often insufficient due to linkage disequilibrium, gene interactions, and regulatory effects. Recent advancements in Large Language Models (LLMs) have demonstrated potential in automating causal gene identification, but their effectiveness remains limited by knowledge representation and retrieval mechanisms. This study builds on previous research by evaluating LLMs for causal gene identification, with a focus on enhancing performance through Retrieval-Augmented Generation (RAG) and the incorporation of genomic distance information. We replicate prior results using smaller model Qwen2.5--assessing their predictive accuracy using a benchmark dataset from Open Targets. We improved the preformences when integrating RAG-based literature retrieval (F1 = 0.795) and gene distance information (F1 = 0.806). However, the combined approach yielded diminishing returns, suggesting interactions between these enhancements. Error analysis revealed that genomic distance features improved predictions by reinforcing established heuristics, while RAG enhanced domain knowledge but occasionally led to semantic biases. These findings highlight the potential of hybrid approaches in leveraging both structured genomic features and unstructured textual data.