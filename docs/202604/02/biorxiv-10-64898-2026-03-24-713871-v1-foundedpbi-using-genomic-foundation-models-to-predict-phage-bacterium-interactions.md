---
title: "FoundedPBI: Using Genomic Foundation Models to predict Phage-Bacterium Interactions"
authors: "Carrillo Barrera, P., Babey, A., Pena, C. A."
date: 2026-03-26
pdf: "https://www.biorxiv.org/content/10.64898/2026.03.24.713871v1.full.pdf"
tags: ["query:med-ai"]
score: 9.0
evidence: 利用基因组基础模型和DNA语言模型
tldr: FoundedPBI利用基因组基础模型通过DNA序列预测噬菌体与细菌的相互作用。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-24-713871-v1/fig-001.webp\", \"caption\": \"Figure 2 Joint UMAP projection of phage embeddings from the three foundation models. The distinct spatial organisation across models confirms that they capture complementary genomic features. Inset: Spearman ρ between pairwise distance matrices computed on the original embeddings.\", \"page\": 5, \"index\": 1, \"width\": 534, \"height\": 470}]"
motivation: 利用基因组基础模型和DNA语言模型。
method: 方法与实现细节请参考摘要与正文。
result: 结果与对比结论请参考摘要与正文。
conclusion: 总体而言，该工作在所述任务上展示了有效性，并提供了可复用的思路或工具。
---

## Abstract
The scalability of phage therapy as a viable alternative or complement to antibiotics is limited by the labor-intensive experimental screening required to identify compatible phage-bacterium pairs. To accelerate this discovery process, we propose FoundedPBI, an ensemble deep learning approach that leverages the emergent capabilities of genomic foundation models, large language models pre-trained on vast DNA corpuses to predict phage-bacterium interactions from DNA sequences alone. We employ an ensemble strategy that aggregates outputs from three state-of-the-art DNA language models into a unified meta-embedding, which is then processed by a neural classifier. Our approach makes two key contributions: (1) We demonstrate that performing ensemble learning across models trained on different genomic data--i.e., prokaryotic (Nucleotide Transformer v2, DNABERT-2) and bacteriophage (MegaDNA) genomes--captures partially-orthogonal biological signals, yielding 6% F1-score improvement over the best individual model. (2) We adapt long-context NLP aggregation strategies to handle whole bacterial and phage genomes (up to 5M base pairs) that exceed the foundation models context windows (12-96K bp) by a factor of 50-100, a critical challenge largely unaddressed in prior genomic deep learning work. On the PredPHI benchmark, FoundedPBI achieves a 76% F1-score outperforming the current state-of-the-art (PBIP) by 7%. On our internal dataset (CI4CB), we achieve 93% F1-score, improving our previous best methods by 4%. These results demonstrate that ensemble learning with proper long-context handling enables effective knowledge transfer of genomic foundation models to specialized prediction tasks.