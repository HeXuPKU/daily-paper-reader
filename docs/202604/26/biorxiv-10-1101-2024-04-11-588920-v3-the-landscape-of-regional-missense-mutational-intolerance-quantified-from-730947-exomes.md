---
title: "The landscape of regional missense mutational intolerance quantified from 730,947 exomes"
title_zh: "基于 730,947 个外显子组量化的区域性错义突变不耐受性图谱"
authors: "Wang, L., Chao, K. R., Panchal, R., Liao, C., Abderrazzaq, H., Ye, R., Schultz, P., Compitello, J., Grant, R. H., Kosmicki, J. A., Weisburd, B., Phu, W., Wilson, M. W., Laricchia, K. M., Goodrich, J. K., Goldstein, D., Goldstein, J. I., Vittal, C., Poterba, T., Baxter, S., Watts, N. A., Solomonson, M., gnomAD consortium,, Tiao, G., Rehm, H. L., Neale, B. M., Talkowski, M. E., MacArthur, D. G., O'Donnell-Luria, A., Karczewski, K. J., Radivojac, P., Daly, M. J., Samocha, K. E."
date: 2026-04-23
pdf: "https://www.biorxiv.org/content/10.1101/2024.04.11.588920v3.full.pdf"
tags: ["query:gwas"]
score: 7.0
evidence: 将错义突变不耐受性与复杂性状遗传力整合
tldr: "本研究利用gnomAD v4.1.1中730,947个外显子组数据，通过对比实际观测与零突变模型，量化了基因内部区域性的错义突变不耐受性。研究发现错义突变缺失区域显著富集了ClinVar致病变异及神经发育障碍相关的新发变异。基于此，研究制定了符合ACMG/AMP标准的致病性评估阈值，并开发了集成的MPC指标，显著提升了对早期发育疾病中罕见错义变异的解读和分层能力。"
source: biorxiv
selection_source: fresh_fetch
motivation: 旨在通过识别基因内部对错义突变具有特定不耐受性的区域，解决错义变异功能影响难以精准评估的问题。
method: 基于大规模外显子组测序数据，利用零突变模型量化分析转录本中不同区域的错义变异约束程度。
result: "发现错义变异比例低于预期36%的区域可提供中等强度的致病性证据，并成功构建了优化的MPC变异致病性评分指标。"
conclusion: 该研究为临床错义变异的解读提供了强有力的区域约束量化工具，有助于提高遗传病诊断的准确性。
---

## 摘要
错义变异的功能影响范围广泛，取决于特定的氨基酸替换以及在基因中的位置等因素。为了解释其致病性，研究一直致力于识别基因内对错义变异特别不耐受的区域。在此，我们利用基因组聚合数据库（gnomAD v4.1.1）中 730,947 个外显子组测序个体的罕见错义变异模式，对照零突变模型，识别出在错义约束方面存在区域差异的转录本。错义变异缺失区域富集了 ClinVar 致病变异、来自神经发育障碍个体的从头错义变异以及复杂性状的遗传力。遵循 ClinGen 对 ACMG/AMP 变异分类指南的校准建议，我们确定在观测到的错义变异少于预期值 36% 的区域内的变异，可达到致病性的中等证据支持。我们将这种区域约束测量整合到一个错义致病性指标（命名为 MPC）中，该指标能有效区分早发性发育障碍患者与对照组中的罕见及从头错义变异。这些结果为辅助错义变异解释提供了额外的工具。

## Abstract
Missense variants can have a range of functional impacts depending on factors such as the specific amino acid substitution and location within the gene. To interpret their deleteriousness, studies have sought to identify regions within genes that are specifically intolerant of missense variation. Here, we leverage the patterns of rare missense variation in 730,947 exome sequenced individuals in the Genome Aggregation Database (gnomAD v4.1.1) against a null mutational model to identify transcripts with regional differences in missense constraint. Missense-depleted regions are enriched for ClinVar pathogenic variants, de novo missense variants from individuals with neurodevelopmental disorders, and complex trait heritability. Following ClinGen calibration recommendations for the ACMG/AMP variant classification guidelines, we establish that variants within regions with <36% of their expected missense variation achieve moderate support for pathogenicity. We integrate this regional constraint measure into a missense deleteriousness metric (named MPC) that effectively stratifies rare and de novo missense variants in individuals with early-onset developmental conditions from controls. These results provide additional tools to aid in missense variant interpretation.