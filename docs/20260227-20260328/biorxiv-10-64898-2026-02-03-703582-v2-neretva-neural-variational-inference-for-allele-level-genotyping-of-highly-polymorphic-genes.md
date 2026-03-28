---
title: "Neretva: Neural Variational Inference for Allele-level Genotyping of Highly Polymorphic Genes"
title_zh: Neretva：用于高多态性基因等位基因水平基因分型的神经变分推断
authors: "Zhou, Q., Ahmadi, S. P., Numanagic, I."
date: 2026-03-16
pdf: "https://www.biorxiv.org/content/10.64898/2026.02.03.703582v2.full.pdf"
tags: ["query:gwas"]
score: 8.0
evidence: 用于基因分型的神经变分推断和自动编码变分贝叶斯
tldr: 高度多态基因家族（如CYP和KIR）的准确基因分型对精准医学至关重要，但受序列相似性和结构复杂性挑战。本文提出Neretva框架，将基因分型建模为概率潜变量模型，并利用自动编码变分贝叶斯（AEVB）进行推理。该方法通过神经推理网络解决了传统方法在可扩展性和灵活性上的不足，在CYP和KIR家族上实现了更优或相当的准确率，为复杂基因组分析提供了高效的新工具。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-02-03-703582-v2/fig-001.webp\", \"caption\": \"Figure 1 Network structure of inference model q(θ,Ψ|Y) and generative model p(Y|θ,Ψ).\", \"page\": 4, \"index\": 1, \"width\": 583, \"height\": 491}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-02-03-703582-v2/fig-002.webp\", \"caption\": \"Table 1. Performance comparison between Neretva and other tools on pharmacogenes and KIR genes. In addition to Neretva, only top three tools are shown here (other tools are shown in Supplementary Table 3). The best results are highlighted in bold.\", \"page\": 5, \"index\": 2, \"width\": 1057, \"height\": 466}]"
motivation: 传统基因分型方法在处理高度多态基因家族时面临序列相似性高、拷贝数变异及计算扩展性差等挑战。
method: 提出Neretva框架，将基因分型问题转化为概率潜变量模型，并采用自动编码变分贝叶斯（AEVB）进行高效推理。
result: 在CYP和KIR基因家族的测试中，Neretva展现出优异的可扩展性，且准确率达到或超过了现有最先进方法的水平。
conclusion: Neretva为复杂基因家族的等位基因水平分型提供了一种灵活且高效的神经变分推理解决方案。
---

## 摘要
对高多态性基因家族进行准确的基因分型和定相（phasing）对于精准医学至关重要。然而，由于相关基因之间极高的序列相似性、拷贝数变异以及结构复杂性，基因分型问题在计算上仍然具有挑战性。目前的方法通常依赖于整数线性规划或基于最大似然的方法，这些方法往往面临可扩展性和灵活性问题。在此，我们提出了 Neretva，这是一个将基因分型问题建模为概率隐变量模型，并采用自动编码变分贝叶斯（AEVB）进行推断的新框架。利用神经推断网络，我们的方法可以高效地扩展到复杂的基因家族，如 CYP（细胞色素 P450）和 KIR（杀伤细胞免疫球蛋白样受体），并在两个家族上都达到了与当前最先进技术相当或更高的准确度。Neretva 是开源的，可在 https://github.com/0xTCG/neretva 免费获取。

## Abstract
Accurate genotyping and phasing of highly polymorphic gene families are essential for precision medicine. Yet, the genotyping problem remains computationally challenging due to extreme sequence similarity between related genes, copy number variation, and structural complexity. Current methods typically rely on integer linear programming or maximum likelihood-based approaches that often suffer from scalability and flexibility issues. Here, we present Neretva, a new framework that models the genotyping problem as a probabilistic latent variable model and employs auto-encoding variational Bayes (AEVB) for inference. Leveraging neural inference networks, our approach scales efficiently to complex gene families such as CYP (cytochrome P450) and KIR (killer-cell immunoglobulin-like receptors), and achieves competitive or improved accuracy over the current state of the art on both families. Neretva is open source and is freely available at https://github.com/0xTCG/neretva.