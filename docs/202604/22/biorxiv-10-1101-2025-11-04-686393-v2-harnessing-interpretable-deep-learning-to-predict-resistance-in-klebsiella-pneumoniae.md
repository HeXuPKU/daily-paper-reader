---
title: Harnessing Interpretable Deep Learning to Predict Resistance in Klebsiella pneumoniae
title_zh: 利用可解释深度学习预测肺炎克雷伯菌的耐药性
authors: "Araujo, N. d. M. F., Chagas, M., Santos, M. F., Pereira, R. F. A., Brum, R. C., Pinheiro, F. R., Silveira, M. C., Dure, F. M., Muller, B. d. L. A., de Souza, A. A. A., Souza, A. B. S. R., de Souza, A. F., Carvalho-Assef, A. P., Moreira, A. d. S., dos Santos, M. T., Cortes, A. M. d. A., Penna, B., Chagas, T., Aguiar-Alves, F., Silva, F. A. B. d."
date: 2026-04-20
pdf: "https://www.biorxiv.org/content/10.1101/2025.11.04.686393v2.full.pdf"
tags: ["query:gwas"]
score: 7.0
evidence: 利用全基因组数据进行细菌分析的深度学习
tldr: 针对抗生素耐药性这一全球健康威胁，本研究开发了DeepMDC深度学习架构，用于从全基因组数据预测肺炎克雷伯菌的耐药性。该模型将基因组建模为多示例学习问题，利用现代霍普菲尔德网络处理所有开放阅读框，并通过注意力机制实现预测结果的可解释性。实验证明，DeepMDC在多种抗生素耐药性预测中表现优异，并能准确识别关键耐药基因，为生物学假设生成提供了有力工具。
source: biorxiv
selection_source: fresh_fetch
motivation: 为了克服细菌基因组标注成本高且模糊的挑战，并提升深度学习在抗生素耐药性预测中的可解释性。
method: 提出一种基于多示例学习（MIL）和现代霍普菲尔德网络的DeepMDC架构，将全基因组序列作为实例包进行处理。
result: 在肺炎克雷伯菌对四种临床抗生素的耐药性预测中取得高分，且注意力机制成功识别出与耐药性高度相关的基因特征。
conclusion: DeepMDC不仅实现了高精度的耐药性预测，其可解释性特征还为发现新的耐药机制和生物学研究提供了重要参考。
---

## 摘要
抗生素耐药性构成日益严重的全球健康威胁，使治疗管理复杂化，并增加了发病率和死亡率。深度学习方法已成为基于组学数据进行细菌分析的有前景的工具，特别是利用基因组信息预测抗生素敏感性。这一任务依赖于识别与耐药机制相关的基因组特征。本文介绍了 DeepMDC，这是一种专为利用全基因组数据进行细菌分析而设计的深度学习架构。鉴于基因或突变层面的精确注释通常成本高昂且存在歧义，表型分类被建模为一个多实例学习（MIL）问题，其中每个基因组被表示为一组具有单一关联标签的实例。DeepMDC 的核心是一个现代 Hopfield 网络（Modern Hopfield Network），用于处理源自基因组数据的所有开放阅读框（ORF），包括小型 ORF。该架构的一个关键特征是其可解释性，通过注意力机制实现，有助于提供生物学见解并生成假设。该模型针对肺炎克雷伯菌和四种临床相关抗生素（美罗培南、头孢吡肟、头孢他啶和庆大霉素）进行了评估，在多项指标上均表现优异。值得注意的是，与耐药性相关的基因在推理过程中始终获得较高的注意力分数，这验证了该架构的有效性，并最终可能产生新的假设。

## Abstract
Antimicrobial resistance constitutes an escalating global health threat, complicating therapeutic management and increasing morbidity and mortality. Deep learning approaches have emerged as promising tools for bacterial profiling based on omics data, particularly for predicting antimicrobial susceptibility from genomic information. This task relies on identifying genomic signatures associated with resistance mechanisms. Here, DeepMDC is introduced as a deep learning architecture designed for bacterial profiling using whole-genome data. Given that precise annotation at the gene or mutation level is often costly and ambiguous, phenotypic classification is formulated as a Multiple Instance Learning (MIL) problem, in which each genome is represented as a bag of instances with a single associated label. The core of DeepMDC is a Modern Hopfield Network that processes all open reading frames (ORFs), including small ones, derived from genomic data. A key feature of the architecture is its interpretability, enabled by attention mechanisms that facilitate biological insight and hypothesis generation. The model was evaluated against Klebsiella pneumoniae and four clinically relevant antibiotics (meropenem, cefepime, ceftazidime, and gentamicin), achieving strong performance in several metrics. Notably, genes associated with resistance consistently received high attention scores during inference, which validates the architecture and eventually may generate new hypotheses.