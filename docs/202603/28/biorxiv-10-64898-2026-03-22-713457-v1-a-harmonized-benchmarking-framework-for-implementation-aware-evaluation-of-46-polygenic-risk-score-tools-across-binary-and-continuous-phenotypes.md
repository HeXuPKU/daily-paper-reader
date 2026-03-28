---
title: A harmonized benchmarking framework for implementation-aware evaluation of 46 polygenic risk score tools across binary and continuous phenotypes
title_zh: 一个用于对 46 种多基因风险评分工具进行实现感知评估的统一基准测试框架，涵盖二元和连续表型
authors: "Muneeb, M., Ascher, D."
date: 2026-03-23
pdf: "https://www.biorxiv.org/content/10.64898/2026.03.22.713457v1.full.pdf"
tags: ["query:gwas"]
score: 10.0
evidence: 46种多基因风险评分(PRS)工具的基准测试框架
tldr: 多基因风险评分（PRS）工具在统计假设和实现复杂度上差异巨大，导致直接比较困难。本研究开发了一个标准化的基准测试框架，在英国生物样本库的多种表型上评估了46种PRS工具。该框架不仅关注预测性能，还综合考量了计算资源消耗和软件鲁棒性，为PRS工具的选择和优化提供了可重复的评估标准。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-22-713457-v1/fig-001.webp\", \"caption\": \"Table 3: Phenotype-level comparison between the null model and the best-performing full model. For each phenotype, the best-performing tool was defined as the method with the largest mean test improvement relative to the null model. ∆ represents the difference between the mean test performance of the full and null models. P-values were obtained using paired Wilcoxon signed-rank tests across the five cross-validation folds, and FDR q-values were calculated across all phenotype–tool comparisons. Note that with five folds, the minimum attainable two-sided Wilcoxon p-value is 0.0625, so reported p-values reflect the power ceiling of the cross-validation design rather than the absence of effect.\", \"page\": 11, \"index\": 1, \"width\": 758, \"height\": 189}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-22-713457-v1/fig-002.webp\", \"caption\": \"Table 2: Improvement in predictive performance of the full model relative to the phenotypespecific null model across PRS tools and phenotypes. For Height, values represent the difference in explained variance (∆R2), whereas for all binary phenotypes, values represent the difference in test AUC (∆AUC). Positive values indicate that the inclusion of the PRS improved prediction beyond that of covariates and principal components alone, whereas negative values indicate reduced performance relative to the null model. Missing values (NA) indicate that no valid result was available for that tool–phenotype combination. Cell colours represent relative improvement patterns within each phenotype column.\", \"page\": 10, \"index\": 2, \"width\": 777, \"height\": 684}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-22-713457-v1/fig-003.webp\", \"caption\": \"Fig. 2: Predictive performance versus operational complexity across 46 PRS tools. Each point represents one PRS tool. The x-axis shows a composite operational complexity score computed as a weighted sum of five normalised components: data input requirements (w = 0.20), LD modelling burden (w = 0.15), log-normalised mean runtime (w = 0.25), normalised mean memory consumption (w = 0.15), and phenotype-level failure rate (w = 0.25), where failure rate is defined as the proportion of 40 phenotype–fold combinations for which no valid result was produced. The y-axis shows average predictive performance across all phenotypes for which the tool produced a valid result, expressed as AUC for binary phenotypes and R2 for the continuous Height phenotype and averaged across all evaluated traits. Dashed lines denote the median complexity score (0.33) and median performance (0.578), dividing the space into four quadrants. Quadrant background shading reflects the mean performance of tools within each quadrant, with deeper shading indicating higher average performance.\", \"page\": 14, \"index\": 3, \"width\": 777, \"height\": 498}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-22-713457-v1/fig-004.webp\", \"caption\": \"Fig. 1: Harmonized benchmarking framework used to evaluate 46 PRS tools across eight phenotypes. The framework standardizes installation, data preparation, hyperparameter definition, and tool execution, followed by cross-validation, performance evaluation, hyperparameter sensitivity analysis, and a structured analysis of the tool’s results.\", \"page\": 3, \"index\": 4, \"width\": 621, \"height\": 506}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-22-713457-v1/fig-005.webp\", \"caption\": \"Fig. 3: Hierarchical clustering of PRS tools based on cross-phenotype similarity of SNP effect sizes. For each phenotype, tool-specific beta estimates were averaged across the five crossvalidation folds and aligned on overlapping SNPs. Pairwise Pearson correlations between tools were then computed and averaged across phenotypes to obtain an overall similarity matrix. The dendrogram was constructed using distance defined as 1 − r, where r is the average pairwise correlation. Tools that cluster more closely produced more similar SNP effect-size profiles across the evaluated phenotypes.\", \"page\": 18, \"index\": 5, \"width\": 698, \"height\": 350}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-22-713457-v1/fig-006.webp\", \"caption\": \"Table 1: Best predictive performance achieved by each PRS tool across the eight phenotypes, reported as test-set performance for the full model. Values for Height are reported as R2, whereas values for all binary phenotypes are reported as AUC. Each entry corresponds to the selected full-model configuration for that tool and phenotype, and NA indicates that no valid result was obtained for that phenotype. Cell colours represent relative performance within each phenotype column.\", \"page\": 9, \"index\": 6, \"width\": 775, \"height\": 607}]"
motivation: 针对现有PRS工具在统计假设、输入要求和实现复杂度上的显著差异，解决缺乏统一评估标准的问题。
method: 开发了一个集成标准化预处理、超参数探索和五折交叉验证的基准测试框架，对46种工具进行多维度评估。
result: 弗里德曼检验显示工具排名存在显著差异，且没有一种方法在所有表型和评估指标下表现最优。
conclusion: PRS工具的表现受统计方法、表型架构、计算需求及软件鲁棒性等多种实际实现因素的共同影响。
---

## 摘要
多基因风险评分（PRS）工具在统计假设、输入要求和实现复杂度方面存在显著差异，使得直接比较十分困难。我们开发了一个统一的、实现感知的基准测试框架，在三种模型配置（空模型、仅 PRS 模型以及 PRS 加协变量模型）下，评估了 46 种 PRS 工具在 7 个二元 UK Biobank 表型和 1 个连续性状上的表现。该框架集成了标准化预处理、工具特定执行、超参数探索，并在高性能计算基础设施上使用五折交叉验证进行统一的下游评估。除了预测性能外，我们还评估了运行时间、内存使用、输入依赖关系和失败模式。对 40 个表型-折叠组合进行的 Friedman 检验确认了工具排名存在显著差异（χ2 = 102.29, p = 2.57 x 10-11），没有任何一种方法是普遍最优的。这些研究结果为 PRS 的比较评估提供了一个可复现的框架，并表明工具的性能不仅受统计方法的影响，还受表型架构、预处理选择、协变量结构、计算需求、软件鲁棒性以及实际实现约束的影响。

## Abstract
Polygenic risk score (PRS) tools differ substantially in statistical assumptions, input requirements, and implementation complexity, making direct comparison difficult. We developed a harmonized, implementation-aware benchmarking framework to evaluate 46 PRS tools across seven binary UK Biobank phenotypes and one continuous trait under three model configurations: null, PRS-only, and PRS plus covariates. The framework integrates standardized preprocessing, tool-specific execution, hyperparameter exploration, and unified downstream evaluation using five-fold cross-validation on high-performance computing infrastructure. In addition to predictive performance, we assessed runtime, memory use, input dependencies, and failure modes. A Friedman test across 40 phenotype-fold combinations confirmed significant differences in tool rankings ({chi}2 = 102.29, p = 2.57 x 10-11), with no single method universally optimal. These findings provide a reproducible framework for comparative PRS evaluation and demonstrate that tool performance is shaped not only by statistical methodology but also by phenotype architecture, preprocessing choices, covariate structure, computational demands, software robustness, and practical implementation constraints.

---

## 论文详细总结（自动生成）

这篇论文介绍了一个针对多基因风险评分（PRS）工具的标准化基准测试框架。以下是对该研究的深入总结：

### 1. 论文的核心问题与整体含义（研究动机和背景）
*   **核心问题**：随着基因组学的发展，涌现了大量多基因风险评分（PRS）计算工具。然而，这些工具在统计假设、输入数据要求（如是否需要个体级数据或仅需汇总统计量）、超参数敏感性以及计算复杂度上存在巨大差异。
*   **研究动机**：现有的评估往往缺乏统一的标准，且大多只关注预测准确性（如 AUC 或 $R^2$），忽略了软件的鲁棒性、计算资源消耗和实际部署的难易程度。
*   **整体含义**：本研究旨在建立一个“实现感知”（implementation-aware）的评估体系，通过统一的流程公平地对比 46 种 PRS 工具，为研究人员选择最适合特定表型和计算环境的工具提供指南。

### 2. 论文提出的方法论
*   **核心思想**：开发一个标准化的基准测试框架，将 PRS 计算流程分解为预处理、工具执行、超参数探索和下游评估四个阶段。
*   **关键技术细节**：
    *   **统一预处理**：标准化 SNP 过滤、等位基因对齐和连锁不平衡（LD）参考面板的处理。
    *   **三模型配置**：评估“空模型”（仅协变量）、“仅 PRS 模型”和“全模型”（PRS + 协变量），以量化 PRS 带来的增量改进。
    *   **超参数优化**：对每种工具进行系统的超参数搜索，确保评估的是各工具的最佳潜力。
    *   **操作复杂度评分**：引入一个综合指标，加权衡量数据输入要求、LD 建模负担、运行时间、内存消耗和失败率。

### 3. 实验设计
*   **数据集**：使用 **UK Biobank (UKB)** 的大规模基因组数据。
*   **表型场景**：涵盖 8 种具有代表性的表型，包括 1 个连续性状（身高）和 7 个二元疾病表型（如 2 型糖尿病、乳腺癌、冠状动脉疾病等）。
*   **对比方法**：共对比了 **46 种 PRS 工具**，涵盖了从经典的剪枝与阈值法（P+T）到复杂的贝叶斯方法和机器学习方法。
*   **Benchmark 标准**：采用五折交叉验证（5-fold CV），使用 AUC（二元）和 $R^2$（连续）作为主要性能指标。

### 4. 资源与算力
*   **算力环境**：实验在高性能计算（HPC）基础设施上运行。
*   **具体消耗**：论文详细记录并分析了每种工具的**运行时间**和**峰值内存使用量**。
*   **说明**：虽然未明确列出具体的 CPU/GPU 型号（如 A100 数量），但强调了计算资源的监控是评估“操作复杂度”的核心组成部分，反映了工具在实际科研环境中的适用性。

### 5. 实验数量与充分性
*   **实验规模**：针对 46 种工具，在 8 种表型上分别进行 5 折交叉验证，总计产生了数百组独立的运行实验。
*   **充分性与公平性**：
    *   **统计验证**：使用了 Friedman 检验和 Wilcoxon 符号秩检验来验证工具间差异的显著性。
    *   **客观性**：通过标准化的输入和自动化的超参数搜索，最大限度地减少了人为调优带来的偏差。
    *   **覆盖面**：实验不仅关注成功的结果，还详细记录了工具在特定情况下的“失败模式”，这在同类研究中较为少见，增加了评估的客观性。

### 6. 论文的主要结论与发现
*   **无“万能工具”**：没有任何一种 PRS 工具在所有表型和所有评估指标下都表现最优。工具的排名随表型的遗传架构（如多基因性）而变化。
*   **性能差异显著**：Friedman 检验确认了工具间的性能排名存在统计学上的显著差异（$p < 2.57 \times 10^{-11}$）。
*   **实现成本与收益的权衡**：一些高复杂度的贝叶斯方法虽然在某些表型上略微领先，但其巨大的计算开销和较高的运行失败率可能使其在实际大规模应用中不如简单的线性模型。
*   **协变量的重要性**：在许多二元疾病预测中，传统协变量（年龄、性别等）贡献了大部分预测能力，PRS 的增量贡献在不同疾病间差异巨大。

### 7. 优点
*   **规模空前**：对比了 46 种工具，是目前该领域最全面的基准测试之一。
*   **多维度评估**：不仅看预测精度，还看“好不好用”（内存、时间、稳定性），具有极高的工程参考价值。
*   **高度可复现**：提供了标准化的框架，方便其他研究者测试新的工具。

### 8. 不足与局限
*   **人群单一性**：主要基于 UK Biobank 的欧洲裔人群，其结论在跨族裔（如东亚或非洲人群）中的泛化性有待验证。
*   **表型覆盖有限**：虽然选择了 8 种表型，但相对于人类数千种性状而言，覆盖面仍有提升空间。
*   **静态评估**：PRS 工具更新极快，基准测试结果具有时效性，需要持续维护更新。
*   **LD 参考面板依赖**：实验结果可能受到所选 LD 参考面板质量的影响，而不同工具对 LD 信息的敏感度不同。

（完）
