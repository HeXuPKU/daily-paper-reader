---
title: Pan-cancer survival modeling reveals structural limits of genomic feature integration in immunotherapy outcomes
title_zh: 泛癌生存建模揭示了免疫治疗预后中基因组特征整合的结构性限制
authors: "Hassan, W., Adeleke, S."
date: 2026-04-20
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.15.718634v2.full.pdf"
tags: ["query:med-ai"]
score: 8.0
evidence: 整合临床和全基因组测序特征的机器学习框架
tldr: 本研究探讨了免疫检查点抑制剂（ICI）治疗中临床与全基因组测序（WGS）特征对生存预测的贡献。通过分析658名患者的数据，研究发现肿瘤突变负荷（TMB）单独预测效果接近随机，而临床变量是预测性能的主要来源。尽管整合了多种基因组特征，但相比优化后的临床模型，性能提升有限。这揭示了在异质性泛癌队列中，临床信号往往掩盖了基因组特征，为未来整合基因组数据的计算方法提供了基准和局限性参考。
source: biorxiv
selection_source: fresh_fetch
motivation: 旨在评估在真实世界泛癌队列中，临床特征与全基因组测序特征在免疫治疗生存预测中的相对贡献及整合局限性。
method: 利用Genomics England的658名患者数据，通过机器学习框架对比了仅TMB、仅临床、临床+TMB及11特征整合模型的预测性能。
result: 临床模型性能显著优于仅TMB模型，而加入基因组特征后的整合模型（C-index 0.60）较临床模型提升微小。
conclusion: 在异质性泛癌背景下，临床信号的主导地位限制了基因组特征对生存预测模型的额外贡献。
---

## 摘要
背景：免疫检查点抑制剂（ICIs）改善了多种癌症类型的预后，但可靠的生存预测因子仍然有限。虽然肿瘤突变负荷（TMB）等基因组特征被广泛使用，但它们在异质性真实世界队列预测建模中的贡献尚不明确。我们评估了临床特征和全基因组测序（WGS）特征在泛癌生存建模中的相对贡献。方法：我们分析了来自英国基因组学（Genomics England）的 658 名接受 ICI 治疗并具有匹配 WGS 数据的患者。使用具有严格训练-测试分离的防泄漏机器学习框架，我们比较了四种模型：仅 TMB 模型、仅临床模型、临床+TMB 模型以及一个集成了 11 个特征的临床-基因组 XGBoost 生存模型。使用 Harrell 一致性指数（C-index）及自助法（bootstrap）置信区间评估模型性能。结果：仅 TMB 表现出接近随机的区分度（C-index 0.50；95% CI 0.44-0.56）。临床变量显著提高了预测性能（0.59；95% CI 0.53-0.64），而添加 TMB 带来的增益微乎其微（0.59）。集成模型达到了 0.60 的 C-index（95% CI 0.55-0.65）。虽然相比仅 TMB 模型有显著改进，但相对于优化后的临床模型，其增量收益较小。特征归因分析显示，模型性能主要由临床变量主导，基因组特征提供的额外信号有限。结论：这些发现表明，在异质性泛癌队列中，预测性能受底层数据结构的约束，其中占主导地位的临床信号掩盖了基因组规模的特征。本研究强调了在不同癌症类型的生存模型中整合基因组数据的根本局限性，并为未来的计算方法提供了基准。

## Abstract
BackgroundImmune checkpoint inhibitors (ICIs) have improved outcomes across multiple cancer types, yet reliable predictors of survival remain limited. While genomic features such as tumor mutational burden (TMB) are widely used, their contribution to predictive modeling in heterogeneous real-world cohorts remains unclear. We evaluated the relative contributions of clinical and whole-genome sequencing (WGS) features in pan-cancer survival modeling.

MethodsWe analyzed 658 patients treated with ICIs with matched WGS data from the Genomics England. Using a leakage-controlled machine learning framework with strict train-test separation, we compared four models: TMB-only, clinical-only, clinical+TMB, and an integrated 11-feature clinico-genomic XGBoost survival model. Model performance was assessed using Harrells concordance index (C-index) with bootstrap confidence intervals.

ResultsTMB alone demonstrated near-random discrimination (C-index 0.50; 95% CI 0.44-0.56). Clinical variables substantially improved predictive performance (0.59; 95% CI 0.53-0.64), with marginal gain from adding TMB (0.59). The integrated model achieved a C-index of 0.60 (95% CI 0.55-0.65). While improvement over TMB alone was significant, incremental gain beyond optimized clinical models was modest. Feature attribution analysis showed that model performance was dominated by clinical variables, with genomic features contributing limited additional signal.

ConclusionsThese findings suggest that, in heterogeneous pan-cancer cohorts, predictive performance is constrained by the underlying data structure, in which dominant clinical signals overshadow genome-scale features. This study highlights fundamental limitations in integrating genomic data into survival models across diverse cancer types and provides a benchmark for future computational approaches.