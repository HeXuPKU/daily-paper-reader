---
title: Environment-aware genomic prediction enhances the transferability of polygenic resistance to ash dieback in Fraxinus excelsior
title_zh: 环境感知型基因组预测增强了欧洲白蜡树对白蜡树枯梢病多基因抗性的可迁移性
authors: "Meger, J., Ulaszewski, B., Burczyk, J."
date: 2026-04-23
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.21.719819v1.full.pdf"
tags: ["query:med-ai"]
score: 8.0
evidence: 为多基因预测建模基因与环境（GxE）的相互作用
tldr: 针对欧洲白蜡树受枯梢病威胁的问题，本研究通过分析波兰境内320棵树的基因组与气候数据，探讨了环境敏感型基因组预测。研究发现抗性具有高度遗传性且呈多基因特性，通过结合环境因子与基因型互作（GxE）模型，显著提升了预测模型在不同环境下的迁移能力和准确性，为白蜡树的辅助迁移和恢复策略提供了科学依据。
source: biorxiv
selection_source: fresh_fetch
motivation: 旨在解决长寿命树种在异质环境下因基因与环境互作导致的基因组预测迁移性差的问题，以应对欧洲白蜡树枯梢病的威胁。
method: 结合波兰全国范围的采样、全基因组SNP数据及气候预测因子，利用多核框架构建包含GxE效应的基因组预测模型并进行内外验证。
result: 发现抗性具有高遗传力，且包含GxE效应的模型在独立验证集中表现稳健（相关性达0.80），显著优于传统主效应模型。
conclusion: 证明了环境感知型基因组预测能增强抗性选育的可靠性，为欧洲白蜡树的辅助迁移和生态恢复提供了有效的技术支撑。
---

## 摘要
由 Hymenoscyphus fraxineus 引起的白蜡树枯梢病威胁着整个分布范围内的欧洲白蜡树（Fraxinus excelsior L.），但自然种群在疾病响应方面仍保留着可遗传的多基因变异。长寿树木基因组预测面临的一个主要挑战是在异质环境中的可迁移性降低，其中基因型与环境（GxE）的相互作用可能会影响表型表达。在本研究中，我们结合了波兰全国范围内的采样（来自 107 个种群的 320 棵树）、全基因组 SNP 数据和气候衍生预测因子，以测试模拟环境相似性和 GxE 是否能提高对白蜡树枯梢病严重程度（使用综合树木受损指数 Syn 进行量化）的预测。环境排序分析确定了一个主要的温湿气候梯度是 Syn 的关键驱动因素（PC1env: β = 0.45 ± 0.14, p = 0.0016），尽管大尺度环境预测因子仅解释了较小比例的表型方差。全基因组关联分析揭示了显著的加性遗传信号（基于 SNP 的遗传力 h²SNP = 0.63；极端表型 h²SNP = 0.81），并鉴定了 414 个暗示性位点（p < 1 x 10⁻⁴），这与广泛的多基因抗性结构一致，但在 2 号和 4 号染色体上的两个候选区域中存在明显的关联信号局部富集。在基因组预测中，性状富集的 SNP 面板在各种标记密度下均一致优于随机面板。对于 500-SNP 面板，内部验证的预测能力达到 r ≈ 0.89，并且在独立外部验证集（n = 64）中保持稳健（r ≈ 0.80）。在多核框架中纳入 GxE 相比于主效应模型取得了适度但一致的提升，特别是在环境外推情况下，REML 方差分量分析支持非零的相互作用组分（VGxE ≈ 14.9% 和 20.9%）。我们的结果表明，白蜡树枯梢病抗性具有可预测的多基因性，且考虑环境异质性增强了基因组预测的稳健性和可迁移性，为欧洲白蜡树恢复中的环境感知选择和辅助迁移策略提供了支持。

## Abstract
Ash dieback caused by Hymenoscyphus fraxineus threatens European ash (Fraxinus excelsior L.) across its range, yet natural populations retain heritable, polygenic variation in disease response. A major challenge for genomic prediction in long-lived trees is reduced transferability across heterogeneous environments, where genotype-by-environment (GxE) interactions may influence phenotypic expression. Here, we combined nationwide sampling across Poland (320 trees from 107 populations), whole-genome SNP data, and climate-derived predictors to test whether modelling environmental similarity and GxE can improve the prediction of ash dieback severity, quantified using a synthetic tree damage index (Syn). Environmental ordination identified a primary hydroclimatic gradient as a key driver of Syn (PC1env: {beta} = 0.45 {+/-} 0.14, p = 0.0016), although broad-scale environmental predictors explained only a modest proportion of phenotypic variance. Genome-wide association analyses revealed substantial additive genetic signal (SNP-based heritability h{superscript 2}SNP = 0.63; extreme-phenotype h{superscript 2}SNP = 0.81) and identified 414 suggestive loci (p < 1 x 10-), consistent with a broadly polygenic architecture of resistance, but with pronounced local enrichment of association signals in two candidate regions on chromosomes 2 and 4. In genomic prediction, trait-enriched SNP panels consistently outperformed random panels across marker densities. Predictive ability reached r {approx} 0.89 in internal validation for a 500-SNP panel and remained robust (r {approx} 0.80) in an independent external validation set (n = 64). Incorporating GxE in a multi-kernel framework yielded modest but consistent gains over main-effect models, particularly under environmental extrapolation, with REML variance partitioning supported a non-zero interaction component (VGxE {approx} 14.9% and 20.9%). Our results demonstrate that ash dieback resistance is predictably polygenic and that accounting for environmental heterogeneity enhances the robustness and transferability of genomic prediction, supporting environment-aware selection and assisted migration strategies for European ash restoration.