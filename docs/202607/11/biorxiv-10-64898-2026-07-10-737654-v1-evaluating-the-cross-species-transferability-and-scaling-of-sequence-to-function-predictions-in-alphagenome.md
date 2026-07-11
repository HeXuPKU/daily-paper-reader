---
title: Evaluating the cross-species transferability and scaling of sequence-to-function predictions in AlphaGenome
title_zh: 评估AlphaGenome中序列-功能预测的跨物种可迁移性与扩展性
authors: "Ramarao-Milne, P., Ma, S., Sng, L., MacPhilamy, C., Yeap, H. L., Oh, K. P., Kuiper, M., Lu, Q., Speight, R., Bauer, D. C."
date: 2026-07-10
pdf: "https://www.biorxiv.org/content/10.64898/2026.07.10.737654v1.full.pdf"
tags: ["query:med-ai"]
score: 7.0
evidence: 评估跨物种深度序列-功能模型AlphaGenome
tldr: AlphaGenome是用于DNA序列到分子表型预测的深度学习模型，此前主要在人基因组上评估。本研究测试其在同属训练集但特征较少的小鼠数据上的表现，发现定量表达效应预测方向偏弱且压缩约100倍，而剪接位点破坏识别跨物种准确度相近（AUC 0.96对0.98）。开发了AI代理自主评估预测置信度的评分方法，通过包裹负责任AI层拦截不可靠结果，符合澳大利亚VAISS标准。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-10-737654-v1/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1812, \"height\": 1004, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-10-737654-v1/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1774, \"height\": 622, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-10-737654-v1/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1749, \"height\": 1467, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-10-737654-v1/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 804, \"height\": 725, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-10-737654-v1/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1408, \"height\": 847, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-10-737654-v1/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1739, \"height\": 862, \"label\": \"Figure\"}]"
motivation: 评估AlphaGenome模型在不同物种间的泛化能力，特别是对小鼠数据，以揭示其预测局限并确保安全应用。
method: 在鼠基因组上测试AlphaGenome的定量表达效应和剪接位点预测，并设计AI代理评分方法自动评估预测置信度，结合负责任AI层过滤不可靠结果。
result: 定量表达效应预测弱且压缩约100倍，剪接位点预测跨物种准确度一致（AUC 0.96 vs 0.98），AI代理评分能有效区分预测可靠区域。
conclusion: AlphaGenome在剪接位点识别上具有跨物种稳健性，但对调控变异预测有局限，需通过负责任AI层包装以确保安全合规使用。
---

## 摘要
直接从DNA序列预测分子表型的深度学习模型为解释基因组变异提供了强大的框架。最近，AlphaGenome被提出作为一种深度序列-功能架构，能够预测历史上需要实验才能获得的观测结果。尽管该模型表现出高准确性，但它主要是在以参考基因组为基准的人类变异上进行评估。在这里，我们测试了其对小鼠数据的性能——这是AlphaGenome训练的另一个物种，但其特征数比人类少五倍（1,128对比5,930）。我们证明了AlphaGenome的预测性能根据功能任务的不同而有显著差异。具体而言，在重建单倍型和单变异模式下，预测的定量表达效应方向较弱，且相对于经验基准约压缩了100倍。相比之下，经典剪接位点破坏的识别在人和小鼠中具有几乎相同的准确性（AUC 0.96对比0.98），预测效应大小未见跨物种差异。我们开发了一种供AI代理自主评估AlphaGenome预测置信度的评分方法，能够准确区分AlphaGenome在不同物种间稳健的序列识别能力与当前解释未精细定位调控变异时的局限性。这展示了如何通过围绕调用包装一个负责任的AI层来拦截有缺陷的结果，从而安全地利用仍在开发中的GenAI创新，并遵守国际标准（例如澳大利亚自愿性AI安全标准VAISS）。

## Abstract
Deep learning models that predict molecular phenotypes directly from DNA sequence offer a powerful framework for interpreting genomic variation. Recently, AlphaGenome was introduced as a deep sequence-to-function architecture capable of predicting observations that historically required experiments. While the model has shown high accuracy, it was primarily evaluated on human variants scored against a reference genome. Here, we test performance on mouse data, the other species AlphaGenome was trained on although with fivefold fewer features than human (1,128 versus 5,930). We demonstrate that AlphaGenome's predictive performance varies considerably depending on the functional task. Specifically, predicted quantitative expression effects are directionally weak and compressed roughly 100-fold relative to empirical benchmarks across both reconstructed-haplotype and single-variant regimes. In contrast, canonical splice-site disruptions are recognized with near-identical accuracy in mouse and human (AUC 0.96 versus 0.98), displaying no cross-species divergence in predicted effect magnitude. We developed a scoring-approach for AI-agents to autonomously assess AlphaGenome prediction confidence and accurately differentiate between AlphaGenome's robust sequence-level recognition across species and its current limitations when interpreting un-fine-mapped regulatory variants. This demonstrates how GenAI innovations that are still under development can safely be harnessed by wrapping a responsible AI layer around the call to intercept flawed results, thereby adhering to international standards, such as the Australian Voluntary AI Safety Standard (VAISS).