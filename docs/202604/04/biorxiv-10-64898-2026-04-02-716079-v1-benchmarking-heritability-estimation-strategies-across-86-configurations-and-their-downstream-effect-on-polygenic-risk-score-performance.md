---
title: Benchmarking Heritability Estimation Strategies Across 86 Configurations and Their Downstream Effect on Polygenic Risk Score Performance
title_zh: 86 种配置下的遗传力估计策略基准测试及其对多基因风险评分性能的下游影响
authors: "Muneeb, M., Ascher, D."
date: 2026-04-02
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.02.716079v1.full.pdf"
tags: ["query:gwas"]
score: 10.0
evidence: 基准测试遗传力估计及其对PRS性能的影响
tldr: 本研究系统评估了86种遗传力（h^2）估计配置对10种UK Biobank表型的影响，并探讨了其对下游多基因风险评分（PRS）性能的传播效应。研究发现，尽管不同算法和参数设置导致遗传力估计值波动巨大（甚至出现负值），但下游PRS的预测准确性对这些波动具有较强的鲁棒性。这一发现强调了遗传力作为配置敏感参数的本质，并建议在报告时应包含完整的估算规范。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-02-716079-v1/fig-001.webp\", \"caption\": \"Table 5 Summary of top 10 configurations per phenotype. Train SD and Test SD are the standard deviations of train and test AUC across the top 10 configurations selected by the delta-constrained rule. ℎ2 range is the difference between the maximum and minimum ℎ2 values among the top 10. A narrow Test SD with a wide ℎ2 range indicates that PRS performance was robust to heritability magnitude within the top-performing configurations.\", \"page\": 14, \"index\": 1, \"width\": 977, \"height\": 529}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-02-716079-v1/fig-002.webp\", \"caption\": \"Table 1 Statement of Significance\", \"page\": 3, \"index\": 2, \"width\": 762, \"height\": 366}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-02-716079-v1/fig-003.webp\", \"caption\": \"Figure 3: Inter-method family correlation matrix for heritability estimates. Pairwise Pearson correlations between all six method families are shown, computed over mean ℎ2 profiles across the ten phenotypes. Hierarchical clustering with average linkage and Euclidean distance was applied to the correlation values to produce the dendrogram. Cell values report the Pearson 𝑟; statistically significant pairs (𝑝 < 0.05) are indicated. Methods within the same family do not show significantly stronger agreement than cross-family pairs (Mann–Whitney 𝑝 = 0.459), indicating that algorithmic class rather than software family membership drives inter-method agreement.\", \"page\": 18, \"index\": 3, \"width\": 977, \"height\": 741}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-02-716079-v1/fig-004.webp\", \"caption\": \"Table 4 Pearson and Spearman correlations between fold-specific ℎ2 and PRS performance. Pearson 𝑟 (Test) quantifies the linear association between ℎ2 and mean test AUC or 𝑅2; Pearson 𝑟 (Train) with training performance; Pearson 𝑟 (Δ) with the train–test gap. Spearman 𝑟 (Test) is the rank-based equivalent. *** 𝑝 < 0.001; ** 𝑝 < 0.01; * 𝑝 < 0.05; ns = not significant.\", \"page\": 13, \"index\": 4, \"width\": 977, \"height\": 611}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-02-716079-v1/fig-005.webp\", \"caption\": \"Figure 2: Distribution of SNP heritability estimates across method families. Each box summarises the mean ℎ2 values produced by one method family across all configurations and phenotypes. The central line is the median, box edges are the interquartile range, and whiskers extend to 1.5×IQR; individual points beyond the whiskers are shown. The dashed red line marks ℎ2 = 0; estimates below this line reflect finite-sample sampling variability in unconstrained Haseman–Elston regression variants and are retained as benchmark outputs. Panel B shows the same estimates as a strip plot coloured by phenotype, illustrating which phenotypes drive extreme values within each family.\", \"page\": 17, \"index\": 5, \"width\": 977, \"height\": 427}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-02-716079-v1/fig-006.webp\", \"caption\": \"Table 2 Sample characteristics and GWAS sources for the 10 retained phenotypes. 𝑁 is the total analytic sample after quality control. Cases and controls are reported for binary phenotypes; body mass index is a continuous trait (denoted by dashes). SNPs (QC) is the number of variants in the post-QC genotype dataset. Common SNPs is the number of variants shared between the GWAS summary statistics file and the post-QC genotype data.\", \"page\": 5, \"index\": 6, \"width\": 977, \"height\": 264}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-02-716079-v1/fig-007.webp\", \"caption\": \"Figure 1: Heatmap of mean SNP heritability estimates across all 86 configurations and 10 phenotypes. Each row corresponds to one unique estimation configuration defined by the tool, model variant, clumping and pruning setting, and number of PCA components included; each column corresponds to one phenotype. Cell values represent the mean ℎ2 averaged across five cross-validation folds for the training set. Grey cells (—) indicate configurations for which no valid estimate was obtained for that phenotype specifically for LDpred2 when the number of variants are less than 15 percent between GWAS and the genotype data in settings when all the snps not excluding Hapmap were used. Negative values are concentrated in unconstrained Haseman–Elston regression configurations and reflect finite-sample sampling variability rather than estimator failure. Fold-level standard errors and 95% confidence intervals for all configurations are reported in Supplementary Table S1 (Heritability Estimates).\", \"page\": 16, \"index\": 7, \"width\": 879, \"height\": 1104}]"
motivation: 旨在量化不同遗传力估计策略带来的变异性，并明确这种变异如何影响下游多基因风险评分（PRS）的预测效能。
method: 利用UK Biobank数据，对比了6个工具家族的86种遗传力估计配置，并将结果输入GCTA-SBLUP和LDpred2-lassosum2框架进行性能评估。
result: 遗传力估计值受算法选择和标准化方式影响显著且波动剧烈，但其数值大小与下游PRS的预测准确度（AUC）之间几乎没有相关性。
conclusion: 遗传力是高度依赖配置的模型参数而非通用稳定标量，且PRS构建过程对遗传力输入的适度波动具有较强的容错性。
---

## 摘要
目的：SNP 遗传力估计值在不同估计策略之间存在显著差异，但其对多基因风险评分 (PRS) 构建的下游影响仍缺乏充分表征。方法：我们针对 10 种 UK Biobank 表型，对涵盖 6 个工具家族（GEMMA、GCTA、LDAK、DPR、LDSC 和 SumHer）和 10 个方法组的 86 种遗传力估计配置进行了基准测试，共获得 844 个配置级估计值。每个估计值均被引入 GCTA-SBLUP 和 LDpred2-lassosum2 PRS 框架，并利用空模型、仅 PRS 模型和全模型在五折交叉验证中进行评估。通过 Mann-Whitney U 检验测试了 11 个二元分析对比，以识别遗传力变异的驱动因素。结果：遗传力估计值范围为 -0.862 至 2.735（均值 = 0.134，标准差 = 0.284），其中 844 个估计值中有 133 个（15.8%）为负值，且集中在无约束估计方案中。11 个分析对比中有 10 个显著影响了遗传力的大小，其中算法选择和 GRM 标准化的影响最为显著。尽管存在这种上游变异性，下游 PRS 测试性能与遗传力大小仅呈弱耦合关系：h^2 与测试 AUC 之间的汇总 Pearson 相关系数在 GCTA-SBLUP 中为 r = -0.023，在 LDpred2-lassosum2 中为 r = +0.014，且均不显著。结论：SNP 遗传力应被视为一个对配置敏感的模型参数，而非一个普遍稳定的标量输入。在报告遗传力估计值时，应始终列出其完整的估计规范；此外，下游 PRS 性能对遗传力输入的适度变化具有较强的鲁棒性。

## Abstract
Objective: SNP heritability estimates vary substantially across estimation strategies, yet the downstream consequences for polygenic risk score (PRS) construction remain poorly characterised. We systematically benchmarked heritability estimation configurations and assessed their propagation into downstream PRS performance. Methods: We benchmarked 86 heritability-estimation configurations spanning six tool families (GEMMA, GCTA, LDAK, DPR, LDSC, and SumHer) and ten method groups across 10 UK Biobank phenotypes, yielding 844 configuration-level estimates. Each estimate was propagated into GCTA-SBLUP and LDpred2-lassosum2 PRS frameworks and evaluated across five cross-validation folds using null, PRS-only, and full models. Eleven binary analytical contrasts were tested using Mann-Whitney U tests to identify drivers of heritability variability. Results: Heritability ranged from -0.862 to 2.735 (mean = 0.134, SD = 0.284), with 133 of 844 estimates (15.8%) being negative and concentrated in unconstrained estimation regimes. Ten of eleven analytical contrasts significantly affected heritability magnitude, with algorithm choice and GRM standardisation showing the largest effects. Despite this upstream variability, downstream PRS test performance was only weakly coupled to heritability magnitude: pooled Pearson correlations between h^2 and test AUC were r = -0.023 for GCTA-SBLUP and r = +0.014 for LDpred2-lassosum2, with both being non-significant. Conclusion: SNP heritability is best interpreted as a configuration-sensitive modelling parameter rather than a universally stable scalar input. Heritability estimates should always be reported alongside their full estimation specification, and downstream PRS performance is comparatively robust to moderate variation in the heritability input.

---

## 论文详细总结（自动生成）

这是一份关于论文《86 种配置下的遗传力估计策略基准测试及其对多基因风险评分性能的下游影响》的结构化总结：

### 1. 核心问题与整体含义
*   **研究动机**：SNP 遗传力（$h^2$）是统计遗传学的核心参数，常作为构建多基因风险评分（PRS）的关键输入。然而，在实际操作中，遗传力估计值高度依赖于所选的工具、数据预处理和统计模型。
*   **核心问题**：不同估计策略导致的遗传力变异究竟有多大？这种“上游”估计的波动会如何传播并影响“下游”PRS 的预测准确性？

### 2. 论文提出的方法论
*   **核心思想**：通过穷举法构建一个大规模基准测试矩阵，系统性地改变遗传力估计的每一个环节，并量化其对最终 PRS 性能的贡献。
*   **关键技术细节**：
    *   **86 种配置**：涵盖了 6 个主流工具家族（GEMMA, GCTA, LDAK, DPR, LDSC, SumHer）和 10 个方法组。
    *   **变异维度**：包括算法选择（REML、HE 回归、矩估计）、遗传相关矩阵（GRM）的构建（中心化 vs 标准化）、协变量处理（是否包含 PCA）、变异位点筛选（是否进行剪枝/聚类）以及输入数据类型（个体级基因型 vs GWAS 汇总统计量）。
    *   **PRS 传播机制**：将估计出的 $h^2$ 输入到两个主流 PRS 框架中：**GCTA-SBLUP**（$h^2$ 直接决定收缩参数 $\lambda$）和 **LDpred2-lassosum2**（$h^2$ 用于参数化正则化网格）。

### 3. 实验设计
*   **数据集**：使用 **UK Biobank (UKB)** 数据，筛选出 10 种具有代表性的表型（包括哮喘、BMI、抑郁症、高血压等）。
*   **基准测试（Benchmark）**：
    *   共生成 **844 个配置级遗传力估计值**。
    *   采用 **五折交叉验证**，确保遗传力在训练集估计，PRS 在独立测试集评估。
*   **对比方法**：对比了 11 个二元分析对比（如“有无协变量”、“不同算法”等），并使用 Mann-Whitney U 检验分析其对 $h^2$ 大小的影响。

### 4. 资源与算力
*   **算力说明**：文中提到研究得到了 **NVIDIA Academic Grant Program** 的支持，暗示使用了 GPU 加速计算。
*   **具体细节**：论文未明确列出具体的 GPU 型号、数量或总训练时长，但考虑到处理 UKB 大规模基因型数据及 86 种配置的重复实验，其计算负荷相当可观。

### 5. 实验数量与充分性
*   **实验规模**：研究非常充分。它不仅在 10 种表型上运行了 86 种配置，还通过交叉验证产生了数千次模型拟合。
*   **客观性与公平性**：
    *   **匹配输入对比**：专门设计了“匹配输入”实验，排除预处理差异，纯粹对比统计估计器的性能。
    *   **多模型评估**：同时评估了空模型、仅 PRS 模型和全模型，以区分遗传信号与人口统计学协变量的贡献。

### 6 主要结论与发现
*   **遗传力极度敏感**：$h^2$ 估计值波动巨大（-0.862 到 2.735），算法选择和 GRM 标准化是最大驱动因素。
*   **负值并非失效**：约 15.8% 的估计值为负，主要出现在无约束的 HE 回归中，这反映了低信噪比下的抽样变异，而非工具错误。
*   **下游 PRS 具有鲁棒性**：这是最重要的发现——**上游遗传力的剧烈波动与下游 PRS 的 AUC 性能几乎不相关**（相关系数 $r \approx 0$）。这意味着 PRS 框架对遗传力输入的适度误差具有很强的容错能力。
*   **表型特异性**：没有一种估计方法在所有表型上都表现最优，遗传力应被视为“配置敏感的模型参数”而非“通用生物学常数”。

### 7. 优点
*   **系统性极强**：首次如此全面地拆解了遗传力估计的每一个超参数对 PRS 的影响。
*   **实用指导意义**：为临床研究者提供了定心丸，即 PRS 的预测效能不会因为遗传力估计方法的微小差异而崩溃。
*   **透明度高**：强调了报告遗传力时必须附带完整的配置说明（Specification）。

### 8. 不足与局限
*   **表型覆盖有限**：仅测试了 10 种表型，可能无法完全代表所有复杂的遗传架构。
*   **祖先偏差**：分析仅限于欧洲裔参与者，结论在其他族裔中的适用性待验证。
*   **样本量限制**：部分表型的个案数较少，可能导致某些估计器在极端配置下不稳定。
*   **GWAS 重叠风险**：外部 GWAS 汇总统计量可能与 UKB 样本存在部分重叠，可能导致预测性能的潜在膨胀。

（完）
