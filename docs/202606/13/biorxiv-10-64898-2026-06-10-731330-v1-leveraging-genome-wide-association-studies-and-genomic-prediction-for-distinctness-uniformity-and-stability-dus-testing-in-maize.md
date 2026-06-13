---
title: "Leveraging genome-wide association studies and genomic prediction for distinctness, uniformity, and stability (DUS) testing in maize"
title_zh: 利用全基因组关联研究和基因组预测进行玉米的特异性、一致性和稳定性（DUS）测试
authors: "Daware, A. v., Hacke, C., Remay, A., Starnberger, P., Schraml, C., Collonnier, C., Laurens, F., Schmid, K. J."
date: 2026-06-12
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.10.731330v1.full.pdf"
tags: ["query:gwas"]
score: 7.0
evidence: 整合GWAS和基因组预测用于玉米DUS测试，直接应用GWAS方法
tldr: 玉米DUS测试依赖表型性状，耗时且易受环境影响。本研究整合352个欧洲玉米杂交种的历史DUS评分与高密度SNP数据，通过GWAS鉴定出18个与12个性状相关的基因组区域和候选基因，开发了诊断标记。结合GWAS标记与XGBoost预测DUS特征，平均准确率达0.67，并在公共数据集验证。结果表明分子标记可提高DUS测试效率，加速品种注册。
source: biorxiv
selection_source: fresh_fetch
motivation: 传统玉米DUS测试基于表型，耗时长且受环境波动影响，亟需分子标记辅助以提高效率与准确性。
method: 整合352个玉米杂交种的DUS评分与SNP数据，利用GWAS鉴定关联位点，并结合XGBoost预测DUS特征评分。
result: 鉴定18个基因组区域与12个DUS性状关联；XGBoost预测平均准确率0.67，公共数据集验证有效。
conclusion: 分子标记可增强玉米DUS测试，实现更快更准的品种注册，支持作物改良。
---

## 摘要
测试特异性、一致性和稳定性（DUS）是植物品种登记的要求，基于表型性状，耗时且对环境变化敏感。基因组学的进展允许用分子标记补充DUS测试，国际植物新品种保护联盟（UPOV）提出了DUS测试中的两种模型。针对玉米描述了一个用例，但由于缺乏合适的标记和经过验证的分析框架，实施一直受到阻碍。我们通过将352个欧洲杂交玉米品种的历史DUS特征评分与高密度全基因组单核苷酸多态性（SNP）数据整合来应对这些挑战。利用全基因组关联研究（GWAS），我们识别了与12个DUS特征相关的18个基因组区域和候选基因，从而能够开发与UPOV模型“特征特异性分子标记”一致的诊断标记。由于大多数DUS性状是多基因的，我们将GWAS指导的标记选择与基于XGBoost的机器学习相结合，以预测DUS特征的评分。这种方法在多个性状上实现了强大的预测性能（平均准确率0.67），展示了其在UPOV模型“在品种集合管理中结合表型和分子距离”下管理参考集合的潜力。两种方法均使用独立的公共USDA-NPGS玉米数据集（>1,700份种质）对两个特征进行了验证，突出了公共数据在方法验证中的价值。我们还识别了历史DUS数据的关键限制，包括不平衡和稀疏的性状表示，并讨论了缓解策略。尽管存在这些限制，我们的结果表明分子标记可以改进玉米DUS测试，实现更快、更准确的品种登记，并支持加速作物改良。

## Abstract
Testing for distinctness, uniformity, and stability (DUS) is a requirement for plant variety registration and based on phenotypic traits, which is time-consuming and sensitive to envi-ronmental variation. Advances in genomics allow to complement DUS testing with molecular markers, for which two models in DUS testing were proposed by the Union for the Protection of New Varieties of Plants (UPOV). A use cases was described for maize, but an implementation has been hindered by a lack of suitable markers and validated analytical frameworks. We ad-dress these challenges by integrating historical DUS characteristics scores from 352 European hybrid maize varieties with high-density genome-wide single nucleotide polymorphism (SNP) data. Using genome-wide association studies (GWAS), we identified 18 genomic regions and candidate genes associated with 12 DUS characteristics, enabling the development of diag-nostic markers consistent with the UPOV model "Characteristic-Specific Molecular Markers". Since most DUS traits are polygenic, we combined GWAS-informed marker selection with XG-Boost-based machine learning to predict notes of DUS characteristics. This approach achieved strong predictive performance across multiple traits (mean accuracy 0.67), demonstrating its potential for managing reference collections under UPOV model "Combining phenotypic and molecular distances in the management of variety collections". Both approaches were validated for two characteristics using independent public USDA-NPGS maize datasets (>1,700 accessions) highlighting the value of public data for method validation. We also identify key limitations of historical DUS data, including imbalanced and sparse trait representation, and discuss mitigation strategies. Despite these constraints, our results demonstrate that molecular markers may improve maize DUS testing, enabling faster, more accurate variety registration and supporting accelerated crop improvement.