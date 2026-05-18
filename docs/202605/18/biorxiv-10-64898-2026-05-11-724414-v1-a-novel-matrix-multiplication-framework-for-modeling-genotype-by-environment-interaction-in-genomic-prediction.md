---
title: A novel matrix multiplication framework for modeling genotype-by-environment interaction in genomic prediction
title_zh: 一种用于基因组预测中基因型与环境互作建模的新型矩阵乘法框架
authors: "Montesinos-Lopez, O. A., Montesinos-Lopez, A., Montesinos-Lopez, J. C., Crossa, J., Dreisigacker, S., Hernandez-Suarez, C. M., Ortiz, R."
date: 2026-05-15
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.11.724414v1.full.pdf"
tags: ["query:med-ai"]
score: 8.0
evidence: 基因组预测中的基因与环境交互作用建模
tldr: "针对植物育种中基因型与环境（GE）交互作用建模的复杂性，本研究提出了一种基于矩阵乘法的新型协方差框架。传统方法多采用Hadamard积，而该方法通过矩阵乘法分解对称分量作为随机效应。在11个小麦和水稻数据集上的测试显示，该方法显著提升了预测准确率（最高达13.2%），为多样化环境下的基因组选择提供了更灵活、高效的建模方案。"
source: biorxiv
selection_source: fresh_fetch
motivation: 传统的Hadamard积模型在捕捉复杂的基因型与环境交互作用时存在局限性，难以充分表征其联合相似性。
method: 提出一种通过基因型和环境核矩阵的矩阵乘法推导协方差结构，并将其分解为对称分量整合进混合模型的新框架。
result: "在11个小麦和水稻多环境数据集中，该方法比传统模型提升了高达13.2%的皮尔逊相关系数，并增强了顶端选择准确性。"
conclusion: 该矩阵乘法框架为GE交互建模提供了灵活且可解释的扩展，能有效提升多样化环境下的基因组预测效能。
---

## 摘要
准确建模基因型与环境（GE）互作对于植物育种中的基因组预测至关重要，但由于复杂的互作结构，这仍然具有挑战性。传统模型通常使用基因型和环境协方差矩阵的 Hadamard 积来捕捉联合相似性，但这可能无法充分表征 GE 的复杂性。在此，我们提出了一种新型框架，该框架通过基因型和环境核的矩阵乘法推导协方差结构，并将其分解为对称分量，作为随机效应纳入混合模型中。通过对 11 个小麦和水稻多环境数据集的评估，该方法始终优于传统的基于 Hadamard 积的模型，Pearson 相关系数定义的预测准确率最高提升了 13.2%，并增强了顶级选择准确率。结合这两种方法获得了最高的性能，表明它们捕捉到了互补的信息。该框架为 GE 互作建模提供了一种灵活、可解释且计算上可行的扩展，有望增强在不同环境条件下基因组选择的有效性。

## Abstract
Accurate modeling of genotype-by-environment (GE) interaction is critical for genomic prediction in plant breeding but remains challenging due to complex interaction structures. Conventional models often use the Hadamard product of genotype and environment covariance matrices to capture joint similarity, which may not fully represent GE complexity. Here we propose a novel framework that derives covariance structures from the matrix multiplication of genotype and environment kernels, decomposing these into symmetric components incorporated as random effects in mixed models. Evaluated for 11 wheat and rice multi-environment datasets and across, this approach consistently outperformed the traditional Hadamard-based model, improving prediction accuracy by up to 13.2% in Pearson's correlation and enhancing top-selection accuracy. Combining both methods yielded the highest performance, indicating complementary information capture. This framework offers a flexible, interpretable, and computationally feasible extension for modeling GE interaction, potentially enhancing genomic selection effectiveness under diverse environmental conditions.