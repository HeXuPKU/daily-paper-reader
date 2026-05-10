---
title: Interpretable neural networks prioritize cancer driver genes from genome-wide dependency landscapes
title_zh: 可解释神经网络从全基因组依赖图谱中筛选癌症驱动基因
authors: "Yin, Q., Chen, L."
date: 2026-05-10
pdf: "https://www.biorxiv.org/content/10.1101/2025.04.28.651122v2.full.pdf"
tags: ["query:gwas"]
score: 7.0
evidence: 连接突变与全基因组依赖性的可解释神经网络
tldr: 识别癌症驱动基因是计算生物学的核心挑战。本研究提出了xNNDriver和xAEDriver两个可解释神经网络框架，通过整合基因组突变、DepMap基因依赖性、通路活性和药物反应数据，量化驱动潜力并学习驱动变异表征。这些模型不仅成功识别了已知的关键驱动基因，还揭示了与代谢、信号传导和免疫调节相关的生物学程序，为发现新的治疗靶点提供了有力工具。
source: biorxiv
selection_source: fresh_fetch
motivation: 旨在从全基因组依赖性景观中更有效地识别癌症驱动基因及其潜在的治疗影响。
method: 开发了监督式通路引导模型xNNDriver和无监督自编码器xAEDriver，分别用于评估突变-依赖性信号和学习潜在的驱动变异表征。
result: 模型成功恢复了主要已知驱动基因，并发现了与药物敏感性和通路活性相关的生物学一致性程序。
conclusion: 可解释的深度学习模型证明了基因依赖性景观蕴含丰富的致癌功能信号，为优先筛选驱动基因和治疗漏洞提供了假设生成框架。
---

## 摘要
识别癌症驱动基因及其治疗影响仍然是计算癌症生物学中的一个核心挑战。我们介绍了 xNNDriver 和 xAEDriver，这是两个可解释的神经网络框架，旨在将癌症突变与全基因组 DepMap 基因依赖性、通路活性和药物反应模式联系起来。xNNDriver 是一个监督式的通路引导模型，用于评估基因的突变状态是否被编码在全基因组依赖图谱中；我们将模型拟合度解释为驱动潜力评分，该评分量化了这种突变-依赖信号的强度，并优先筛选具有广泛功能足迹的基因。在 3,008 个候选基因中，xNNDriver 找回了主要的已确定的驱动基因，并突出了文献支持的候选基因，而通路分析揭示了与代谢、生长因子信号传导和免疫调节相关的生物学一致性程序。为了捕捉组合功能状态，xAEDriver 使用无监督自编码器来学习驱动变异表示（DVRs），即由已知驱动突变的频率分布引导的潜在二元特征。DVRs 捕捉了细胞系特异性的依赖模式和表达模式，并与药物敏感性和通路活性相关联。总之，这些可解释的深度学习模型表明，基因依赖图谱编码了丰富的、可解释的致癌功能信号，并为进一步实验验证驱动基因、通路和治疗漏洞提供了一个产生假设的框架。

## Abstract
Identifying cancer driver genes and their therapeutic impact remains a core challenge in computational cancer biology. We introduce xNNDriver and xAEDriver, two interpretable neural network frameworks that connect cancer mutations with genome-wide DepMap gene dependencies, pathway activity, and drug-response patterns. xNNDriver is a supervised pathway-guided model that evaluates whether a gene's mutation status is encoded in the genome-wide dependency landscape; we interpret model fitness as a driver potential score, which quantifies the strength of this mutation-dependency signal and prioritizes genes with broad functional footprints. Across 3,008 candidate genes, xNNDriver recovers major established drivers and highlights literature-supported candidates, while pathway analyses reveal biologically coherent programs related to metabolism, growth factor signaling, and immune regulation. To capture combinatorial functional states, xAEDriver uses an unsupervised autoencoder to learn Driver Variant Representations (DVRs), latent binary features guided by the frequency distribution of known driver mutations. DVRs capture cell-line-specific dependency patterns and expression patterns and are associated with drug sensitivity and pathway activity. Together, these interpretable deep learning models demonstrate that gene dependency landscapes encode rich, interpretable signals of oncogenic function and provide a hypothesis-generating framework for prioritizing drivers, pathways, and therapeutic vulnerabilities for further experimental validation.