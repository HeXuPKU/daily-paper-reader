---
title: Interpretable machine learning meets systems biology to decode genotype-phenotype maps
title_zh: 可解释机器学习结合系统生物学解码基因型-表型映射
authors: "Reguna Madhan, R. L., Balaji, R., Sinha, H., Bhatt, N."
date: 2026-03-18
pdf: "https://www.biorxiv.org/content/10.64898/2026.03.16.712082v1.full.pdf"
tags: ["query:gwas"]
score: 9.0
evidence: 用于精细定位和连锁位点去相关的机器学习方法
tldr: "针对连锁不平衡限制QTL因果基因识别的问题，本研究开发了一个可解释机器学习框架，用于捕捉高阶非线性基因型-表型关系。通过对酿酒酵母在化学压力下的分析，该方法实现了超过75%的预测准确率，并利用SHAP分析和系统生物学模型整合，成功识别了关键因果基因及代谢通路。研究不仅验证了已知基因，还发现了PDR8在细胞壁完整性中的新功能，为从遗传关联转向机械生物学见解提供了新途径。"
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-16-712082-v1/fig-001.webp\", \"caption\": \"Figure 4: Genome-scale metabolic model analysis identifies growth-associated pathways.\", \"page\": 25, \"index\": 1, \"width\": 979, \"height\": 897}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-16-712082-v1/fig-002.webp\", \"caption\": \"Figure 5: Gene regulatory network reveals novel PDR8 function.\", \"page\": 26, \"index\": 2, \"width\": 979, \"height\": 1183}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-16-712082-v1/fig-003.webp\", \"caption\": \"Figure 3: Superior recovery of pleiotropic effector genes.\", \"page\": 23, \"index\": 3, \"width\": 979, \"height\": 1050}]"
motivation: 传统的QTL分析受限于连锁不平衡，难以从关联区域中精准识别因果基因并理解其背后的复杂生物学机制。
method: 开发了一种结合SHAP解释技术与系统生物学模型（如代谢模型和基因网络）的可解释机器学习框架，用于统计去相关并评估遗传变异。
result: "该框架在酵母表型预测中达到75%以上的准确率，识别多效性基因的效率显著优于传统方法，并发现了PDR8基因在蛋白质曼诺基化中的新功能。"
conclusion: 可解释机器学习与系统生物学的集成能够将统计上的基因关联转化为具体的机械生物学洞察，有效解码复杂的基因型-表型映射。
---

## 摘要
从数量性状位点（QTL）中解析因果基因从根本上仍受限于连锁不平衡。我们开发了一个可解释的机器学习框架，该框架能够捕捉高阶非线性基因型-表型关系，并允许对遗传变异进行条件评估，从而实现连锁位点的统计去相关。将该方法应用于不同化学压力条件下的酿酒酵母（Saccharomyces cerevisiae）分离株，我们的方法实现了超过 75% 的预测准确率，并识别出已知的因果基因，包括 MKT1（基因毒性压力）和 IRA2（渗透压力）。基于 SHAP 的分析找回了 56% 经验证的多效性基因，而传统的列联测试仅为 36%。与全基因组尺度代谢模型的整合揭示了区分高生长菌株的通路富集，包括碳转运、糖酵解和氧化磷酸化。值得注意的是，基因调控网络分析识别出 PDR8 在蛋白质甘露糖基化和细胞壁完整性中的新功能，这些功能超出了其在抗药性中的作用。该框架表明，可解释机器学习与系统生物学相结合，能将 QTL 关联转化为机制性的生物学见解。

## Abstract
Resolving causal genes from quantitative trait loci (QTL) remains fundamentally limited by linkage disequilibrium. We developed an interpretable machine learning framework that captures higher-order nonlinear genotype-phenotype relationships and allows conditional evaluation of genetic variants, enabling statistical decorrelation of linked loci. Applied to Saccharomyces cerevisiae segregants across chemical stress conditions, our method achieved >75% prediction accuracy and identified known causal genes, including MKT1 (genotoxic stress) and IRA2 (osmotic stress). SHAP-based analysis recovered 56% of the validated pleiotropic genes, compared with 36% by conventional contingency testing. Integration with genome-scale metabolic models revealed pathway enrichments distinguishing high-growing strains, including carbon transport, glycolysis, and oxidative phosphorylation. Notably, gene regulatory network analysis identified a novel function for PDR8 in protein mannosylation and cell wall integrity--functions extending beyond its role in drug resistance. This framework demonstrates that interpretable machine learning, coupled with systems biology, transforms QTL associations into mechanistic biological insight.