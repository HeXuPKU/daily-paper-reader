---
title: Benchmarking Heritability Estimation Strategies Across 86 Configurations and Their Downstream Effect on Polygenic Risk Score Performance
title_zh: 86种配置下的遗传力估计策略基准测试及其对多基因风险评分性能的下游影响
authors: "Muneeb, M., Ascher, D."
date: 2026-04-02
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.02.716079v1.full.pdf"
tags: ["query:gwas"]
score: 10.0
evidence: 基准测试遗传率估计及其对PRS的影响
tldr: 本研究系统评估了86种遗传力（h^2）估计配置对多基因风险评分（PRS）性能的影响。通过对UK Biobank中10种表型的844个估计值进行基准测试，发现虽然不同算法和配置导致遗传力估计值波动巨大甚至出现负值，但下游PRS的预测准确性对这些波动具有较强的鲁棒性。研究强调了遗传力作为配置敏感参数的特性，并建议在报告时提供完整规格。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-02-716079-v1/fig-001.webp\", \"caption\": \"Table 5 Summary of top 10 configurations per phenotype. Train SD and Test SD are the standard deviations of train and test AUC across the top 10 configurations selected by the delta-constrained rule. ℎ2 range is the difference between the maximum and minimum ℎ2 values among the top 10. A narrow Test SD with a wide ℎ2 range indicates that PRS performance was robust to heritability magnitude within the top-performing configurations.\", \"page\": 14, \"index\": 1, \"width\": 977, \"height\": 529}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-02-716079-v1/fig-002.webp\", \"caption\": \"Table 1 Statement of Significance\", \"page\": 3, \"index\": 2, \"width\": 762, \"height\": 366}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-02-716079-v1/fig-003.webp\", \"caption\": \"Figure 3: Inter-method family correlation matrix for heritability estimates. Pairwise Pearson correlations between all six method families are shown, computed over mean ℎ2 profiles across the ten phenotypes. Hierarchical clustering with average linkage and Euclidean distance was applied to the correlation values to produce the dendrogram. Cell values report the Pearson 𝑟; statistically significant pairs (𝑝 < 0.05) are indicated. Methods within the same family do not show significantly stronger agreement than cross-family pairs (Mann–Whitney 𝑝 = 0.459), indicating that algorithmic class rather than software family membership drives inter-method agreement.\", \"page\": 18, \"index\": 3, \"width\": 977, \"height\": 741}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-02-716079-v1/fig-004.webp\", \"caption\": \"Table 4 Pearson and Spearman correlations between fold-specific ℎ2 and PRS performance. Pearson 𝑟 (Test) quantifies the linear association between ℎ2 and mean test AUC or 𝑅2; Pearson 𝑟 (Train) with training performance; Pearson 𝑟 (Δ) with the train–test gap. Spearman 𝑟 (Test) is the rank-based equivalent. *** 𝑝 < 0.001; ** 𝑝 < 0.01; * 𝑝 < 0.05; ns = not significant.\", \"page\": 13, \"index\": 4, \"width\": 977, \"height\": 611}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-02-716079-v1/fig-005.webp\", \"caption\": \"Figure 2: Distribution of SNP heritability estimates across method families. Each box summarises the mean ℎ2 values produced by one method family across all configurations and phenotypes. The central line is the median, box edges are the interquartile range, and whiskers extend to 1.5×IQR; individual points beyond the whiskers are shown. The dashed red line marks ℎ2 = 0; estimates below this line reflect finite-sample sampling variability in unconstrained Haseman–Elston regression variants and are retained as benchmark outputs. Panel B shows the same estimates as a strip plot coloured by phenotype, illustrating which phenotypes drive extreme values within each family.\", \"page\": 17, \"index\": 5, \"width\": 977, \"height\": 427}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-02-716079-v1/fig-006.webp\", \"caption\": \"Table 2 Sample characteristics and GWAS sources for the 10 retained phenotypes. 𝑁 is the total analytic sample after quality control. Cases and controls are reported for binary phenotypes; body mass index is a continuous trait (denoted by dashes). SNPs (QC) is the number of variants in the post-QC genotype dataset. Common SNPs is the number of variants shared between the GWAS summary statistics file and the post-QC genotype data.\", \"page\": 5, \"index\": 6, \"width\": 977, \"height\": 264}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-02-716079-v1/fig-007.webp\", \"caption\": \"Figure 1: Heatmap of mean SNP heritability estimates across all 86 configurations and 10 phenotypes. Each row corresponds to one unique estimation configuration defined by the tool, model variant, clumping and pruning setting, and number of PCA components included; each column corresponds to one phenotype. Cell values represent the mean ℎ2 averaged across five cross-validation folds for the training set. Grey cells (—) indicate configurations for which no valid estimate was obtained for that phenotype specifically for LDpred2 when the number of variants are less than 15 percent between GWAS and the genotype data in settings when all the snps not excluding Hapmap were used. Negative values are concentrated in unconstrained Haseman–Elston regression configurations and reflect finite-sample sampling variability rather than estimator failure. Fold-level standard errors and 95% confidence intervals for all configurations are reported in Supplementary Table S1 (Heritability Estimates).\", \"page\": 16, \"index\": 7, \"width\": 879, \"height\": 1104}]"
motivation: 旨在探究不同遗传力估计策略产生的变异如何传播并影响下游多基因风险评分（PRS）的预测性能。
method: 系统对比了6个工具家族的86种估计配置，并将生成的844个遗传力估计值应用于两种主流PRS构建框架进行验证。
result: 尽管遗传力估计值受算法和标准化方式影响呈现剧烈波动，但其数值大小与下游PRS的预测准确度之间并无显著相关性。
conclusion: 遗传力应被视为对配置敏感的模型参数而非稳定标量，且PRS性能对遗传力输入的适度变化表现出较强的鲁棒性。
---

## 摘要
目的：SNP遗传力估计值在不同估计策略之间存在显著差异，但其对多基因风险评分（PRS）构建的下游影响尚未得到充分表征。方法：我们对涵盖6个工具家族（GEMMA、GCTA、LDAK、DPR、LDSC和SumHer）和10个方法组的86种遗传力估计配置进行了基准测试，涉及10个UK Biobank表型，共产生844个配置级估计值。每个估计值被代入GCTA-SBLUP和LDpred2-lassosum2 PRS框架，并使用空模型、仅PRS模型和全模型在五折交叉验证中进行评估。通过Mann-Whitney U检验测试了11个二元分析对比，以识别遗传力变异的驱动因素。结果：遗传力范围为-0.862至2.735（均值=0.134，标准差=0.284），844个估计值中有133个（15.8%）为负值，且集中在无约束估计方案中。11个分析对比中有10个显著影响遗传力大小，其中算法选择和GRM标准化显示出最大的影响。尽管存在这种上游变异性，下游PRS测试性能与遗传力大小仅呈弱耦合：GCTA-SBLUP的h^2与测试AUC之间的汇总皮尔逊相关系数为r = -0.023，LDpred2-lassosum2为r = +0.014，两者均不显著。结论：SNP遗传力最好被解释为一个对配置敏感的模型参数，而非一个普遍稳定的标量输入。报告遗传力估计值时应始终附带其完整的估计规范，且下游PRS性能对遗传力输入的适度变化具有较强的鲁棒性。

## Abstract
Objective: SNP heritability estimates vary substantially across estimation strategies, yet the downstream consequences for polygenic risk score (PRS) construction remain poorly characterised. We systematically benchmarked heritability estimation configurations and assessed their propagation into downstream PRS performance. Methods: We benchmarked 86 heritability-estimation configurations spanning six tool families (GEMMA, GCTA, LDAK, DPR, LDSC, and SumHer) and ten method groups across 10 UK Biobank phenotypes, yielding 844 configuration-level estimates. Each estimate was propagated into GCTA-SBLUP and LDpred2-lassosum2 PRS frameworks and evaluated across five cross-validation folds using null, PRS-only, and full models. Eleven binary analytical contrasts were tested using Mann-Whitney U tests to identify drivers of heritability variability. Results: Heritability ranged from -0.862 to 2.735 (mean = 0.134, SD = 0.284), with 133 of 844 estimates (15.8%) being negative and concentrated in unconstrained estimation regimes. Ten of eleven analytical contrasts significantly affected heritability magnitude, with algorithm choice and GRM standardisation showing the largest effects. Despite this upstream variability, downstream PRS test performance was only weakly coupled to heritability magnitude: pooled Pearson correlations between h^2 and test AUC were r = -0.023 for GCTA-SBLUP and r = +0.014 for LDpred2-lassosum2, with both being non-significant. Conclusion: SNP heritability is best interpreted as a configuration-sensitive modelling parameter rather than a universally stable scalar input. Heritability estimates should always be reported alongside their full estimation specification, and downstream PRS performance is comparatively robust to moderate variation in the heritability input.

---

## 论文详细总结（自动生成）

这是一份关于论文《Benchmarking Heritability Estimation Strategies Across 86 Configurations and Their Downstream Effect on Polygenic Risk Score Performance》的结构化总结：

### 1. 论文的核心问题与整体含义
*   **研究动机**：SNP 遗传力（$h^2$）是统计遗传学中的核心参数，用于衡量表型变异中可归因于加性遗传效应的比例。然而，在实际操作中，遗传力估计值高度依赖于所选的工具、算法和数据预处理配置。
*   **核心问题**：目前缺乏系统性的基准测试来揭示这些“上游”遗传力估计的变异如何传播并影响“下游”多基因风险评分（PRS）的预测性能。本研究旨在探究 PRS 性能是否对遗传力输入的波动敏感。

### 2. 论文提出的方法论
*   **核心思想**：通过构建一个包含 86 种不同配置的基准测试矩阵，系统评估软件工具、算法模型、遗传相关矩阵（GRM）构建方式及预处理步骤对遗传力估计的影响，并将其作为输入参数代入 PRS 模型。
*   **关键技术细节**：
    *   **遗传力估计**：涵盖了 6 个工具家族（GEMMA, GCTA, LDAK, DPR, LDSC, SumHer），涉及线性混合模型（LMM）、贝叶斯方法、Haseman–Elston (HE) 回归和 LD 得分回归等。
    *   **PRS 框架**：使用了两种主流框架：
        1.  **GCTA-SBLUP**：遗传力直接决定收缩参数 $\lambda = m(1/h^2 - 1)$，其中 $m$ 是 SNP 数量。
        2.  **LDpred2-lassosum2**：遗传力用于参数化正则化网格。
    *   **分析对比**：定义了 11 个二元对比（如：是否进行剪枝/修剪、HE 回归 vs REML 算法、中心化 vs 标准化 GRM 等），通过 Mann–Whitney U 检验量化各因素对 $h^2$ 的贡献。

### 3. 实验设计
*   **数据集**：使用 **UK Biobank (UKB)** 的基因型数据，筛选出 10 种具有代表性的表型（9 种二元表型如哮喘、高血压、抑郁症，1 种连续表型 BMI）。
*   **Benchmark 设置**：
    *   **样本处理**：仅限欧洲裔参与者，采用五折交叉验证（80% 训练，20% 测试）。
    *   **对比方法**：86 种估计配置 $\times$ 10 种表型，共生成 844 个有效的配置级估计值。
    *   **评估指标**：二元表型使用 AUC（曲线下面积），连续表型使用 $R^2$（解释方差）。

### 4. 资源与算力
*   **算力说明**：文中提到研究得到了 NVIDIA Academic Grant Program 的支持。
*   **具体细节**：论文**未明确列出**具体的 GPU 型号、数量或具体的训练/计算总时长。主要计算任务涉及大规模矩阵运算（GRM 构建）和迭代优化（REML 估计）。

### 5. 实验数量与充分性
*   **实验规模**：进行了 844 组遗传力估计实验，并将其全部传播至两种 PRS 框架中进行下游验证。
*   **充分性与公平性**：
    *   实验设计较为充分，涵盖了从数据预处理（Clumping/Pruning）到模型选择的全流程。
    *   通过“匹配输入（Matched-input）”控制实验，排除了预处理差异，纯粹对比统计估计器的性能，保证了对比的客观性。
    *   采用了交叉验证来评估估计值的稳定性和泛化能力。

### 6. 主要结论与发现
*   **遗传力高度敏感**：$h^2$ 估计值波动剧烈（-0.862 到 2.735），极度依赖于算法选择（REML vs HE）和 GRM 标准化方式。
*   **负遗传力现象**：约 15.8% 的估计值为负，主要出现在无约束的估计器（如 HE 回归）中，这通常反映了低信号背景下的抽样变异，而非算法失效。
*   **下游鲁棒性（核心发现）**：尽管上游遗传力估计变异巨大，但下游 PRS 的测试性能与之**几乎不相关**（相关系数 $r \approx 0$）。这意味着 PRS 模型对遗传力输入的适度误差具有较强的容忍度。
*   **配置建议**：没有单一的估计方法在所有表型中始终占优，遗传力应被视为一个“配置敏感的模型参数”而非“绝对生物学标量”。

### 7. 优点
*   **系统性极强**：首次大规模、多维度地拆解了遗传力估计的每一个环节（如 SNP 筛选、协变量加入、算法类型）对 PRS 的影响。
*   **实战指导意义**：为临床研究者提供了明确建议——报告遗传力时必须附带完整的配置规格，否则数值失去比较意义。
*   **揭示了鲁棒性**：缓解了研究者对于“遗传力估计不准会导致 PRS 失效”的过度担忧。

### 8. 不足与局限
*   **表型覆盖有限**：仅测试了 10 种表型，可能无法完全代表所有复杂的遗传架构。
*   **群体偏差**：分析仅限于欧洲裔样本，结论在其他族裔（如非洲裔、东亚裔）中的适用性有待验证。
*   **数据重叠风险**：外部 GWAS 汇总统计数据可能与 UKB 样本存在部分重叠，这可能在一定程度上高估了 PRS 的绝对性能（尽管不影响 $h^2$ 变异性的对比）。
*   **启发式选择**：文中提出的配置选择启发式方法（Delta-constrained）属于探索性分析，尚未经过完全独立的外部验证。

（完）
