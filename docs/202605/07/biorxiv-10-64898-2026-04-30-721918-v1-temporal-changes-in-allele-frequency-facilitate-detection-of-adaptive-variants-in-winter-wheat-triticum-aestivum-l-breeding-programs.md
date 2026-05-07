---
title: Temporal changes in allele frequency facilitate detection of adaptive variants in winter wheat (Triticum aestivum L.) breeding programs
title_zh: 等位基因频率的时间变化有助于冬小麦（Triticum aestivum L.）育种计划中适应性变异的检测
authors: "Johansen, N. H., Sarup, P., Hansen, P., Orabi, J., Jahoor, A., Ramstein, G. P."
date: 2026-05-04
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.30.721918v1.full.pdf"
tags: ["query:gwas"]
score: 9.0
evidence: 利用等位基因频率随时间变化的趋势来检测变异的GWAS替代方法
tldr: 本研究提出了一种通过追踪冬小麦育种群体八年间等位基因频率时间趋势来识别非中性遗传变异的新方法。研究利用广义线性模型推断选择信号，并分析了这些变异与产量及蛋白质含量的关联。结果证明，该方法能有效识别与关键农艺性状相关的适应性变异，为传统定量遗传学提供了补充，使育种者无需表型数据即可在育种早期检测到受选择的变异。
source: biorxiv
selection_source: fresh_fetch
motivation: 旨在探索一种不依赖表型数据、通过等位基因频率的时间动态变化来识别育种群体中受选择非中性变异的替代方法。
method: 采用广义线性模型对冬小麦八年间的等位基因频率进行建模以推断选择信号，并评估其对表型关联及基因组预测模型的影响。
result: 成功识别出与产量增加正相关及与蛋白质含量下降负相关的选择信号，尽管这些信息未能提高基因组预测的准确性。
conclusion: 等位基因频率的时间趋势分析是检测适应性变异的有效工具，可作为传统方法的补充，助力育种早期阶段的变异筛选。
---

## 摘要
在数量遗传学中，候选 SNP 通常通过全基因组关联研究（GWAS）推断的基因型-表型关联来识别。在本研究中，我们探索了一种替代方法，通过追踪冬小麦（Triticum aestivum L.）育种群体在八年期间等位基因频率的时间趋势来检测具有非中性效应的遗传变异，并从中推断选择信号。我们利用广义线性模型推断选择特征，将等位基因频率的趋势建模为时间（杂交年份）的函数。这些选择特征被用于对变异进行优先级排序。随后，我们研究了表型表现与优先级变异的个体负荷之间的关联。此外，我们评估了将选择信息纳入基因组最佳线性无偏预测（GBLUP）模型是否能提高模型在拟合质量和预测能力方面的性能。研究结果表明，推断出的选择信号在识别非中性变异方面是有效的。受到强烈负向选择的变异与经产量调整后的蛋白质含量下降相关（p 值 < 0.01），而受到中等至高水平正向选择的遗传变异与产量增加相关（p 值 < 0.01）。然而，纳入选择信息并未提高预测准确性。总之，等位基因频率的时间趋势可用于检测非中性变异。因此，所提出的方法可以补充用于检测非中性遗传变异的传统数量遗传学方法。这种方法可能使育种者能够在育种周期的早期检测到非中性变异，而无需依赖表型数据。

## Abstract
In quantitative genetics, candidate SNPs are identified through genotype-phenotype associations inferred with genome-wide association studies (GWAS). In this study, we explore an alternative approach to detect genetic variants with non-neutral effects by tracking temporal trends in allele frequency in a winter wheat (Triticum aestivum L.) breeding population over an eight-year period, from which signals of selection may be inferred. Selection signatures were inferred with a generalized linear model, where we modeled trends in allele frequency as a function of time (crossing year). These signatures of selection were used to prioritize variants. Associations between phenotypic performance and individual load of prioritized variants were then investigated. Furthermore, we assessed whether incorporating selection information into a genomic best linear unbiased prediction (GBLUP) model improves model performance in terms of quality of fit and prediction ability. Our findings indicate that the inferred signals of selection are effective in identifying non-neutral variants. Variants under strong negative selection were associated with a decrease in protein content adjusted for grain yield (p-value < 0.01), while genetic variants that had been under moderate to high levels of positive selection were associated with increased grain yield (p-value < 0.01). However, incorporating selection information did not improve prediction accuracy. In conclusion, temporal trends in allele frequency can be used to detect non-neutral variants. The proposed approach may hence complement traditional quantitative genetic methods for detecting non-neutral genetic variation. This approach may allow breeders to detect non-neutral variants earlier in the breeding cycle, without resorting to phenotypic data.

---

## 论文详细总结（自动生成）

这篇论文探讨了利用育种群体中等位基因频率的时间动态变化来识别受选择影响的遗传变异，为冬小麦育种提供了一种不依赖表型数据的变异检测新思路。以下是对该论文的深度总结：

### 1. 核心问题与整体含义（研究动机和背景）
*   **核心问题**：传统的全基因组关联研究（GWAS）依赖于大规模且昂贵的表型数据采集，且通常在育种周期的后期才能进行。本文旨在探索：是否可以通过追踪育种群体在多年间**等位基因频率（Allele Frequency）的变化趋势**，来识别那些对产量或品质有贡献的“非中性”遗传变异？
*   **研究背景**：在育种过程中，人工选择会导致有利等位基因频率上升，不利基因频率下降。这种时间上的频率偏移包含了选择压力的信号，理论上可以用来识别关键的农艺性状位点，而无需即时的表型观测。

### 2. 论文提出的方法论
*   **核心思想**：将等位基因频率建模为时间的函数，通过统计学模型推断选择系数（Selection Coefficient），并以此对单核苷酸多态性（SNP）进行优先级排序。
*   **关键技术细节**：
    *   **广义线性模型（GLM）**：研究者使用 GLM 对 8 年间（2014-2021）的等位基因频率进行建模。自变量为杂交年份（Crossing Year），因变量为等位基因计数，假设服从二项分布。
    *   **选择信号推断**：通过模型估计出的回归系数来衡量选择强度。
    *   **变异优先级排序**：根据选择信号的显著性和方向，将 SNP 分为受正向选择、负向选择或中性进化的类别。
    *   **验证手段**：计算个体在特定优先级 SNP 类别下的“遗传负荷”（Load），并将其与表型（产量、蛋白质含量）进行关联分析；同时将选择信息整合进基因组最佳线性无偏预测（GBLUP）模型中。

### 3. 实验设计
*   **数据集**：使用了来自丹麦育种计划的 **10,154 株冬小麦** 样本，涵盖了从 2014 年到 2021 年的 8 个育种年度。
*   **基因型数据**：包含 **14,354 个 SNP** 标记。
*   **表型性状**：主要关注**谷物产量（GY）**和**蛋白质含量（PC）**（以及经产量调整后的蛋白质含量）。
*   **Benchmark（基准）**：
    *   传统的 **GWAS** 分析。
    *   标准的 **GBLUP** 基因组预测模型（不含选择权重）。
*   **对比方法**：对比了基于不同选择强度阈值筛选出的 SNP 子集对表型解释力的差异。

### 4. 资源与算力
*   **算力说明**：论文中**未明确说明**具体的硬件配置（如 GPU 型号或数量）及总训练时长。考虑到所使用的 GLM 和 GBLUP 模型在 10k 样本量下的计算量，通常在高性能工作站或小型服务器集群上即可完成，不涉及超大规模深度学习所需的算力资源。

### 5. 实验数量与充分性
*   **实验规模**：研究分析了长达 8 年的连续育种数据，样本量超过一万，这在植物育种研究中具有较好的代表性。
*   **充分性评价**：
    *   实验设计了**交叉验证**来评估预测能力。
    *   进行了**关联分析**来验证推断出的选择信号是否真的与表型相关。
    *   **客观性**：通过对比正向选择和负向选择对不同性状的影响，揭示了产量与蛋白质含量之间的权衡关系（Trade-off），实验逻辑较为严密。

### 6. 主要结论与发现
*   **有效性验证**：等位基因频率的时间趋势确实能有效识别非中性变异。
*   **性状关联**：
    *   受到**强烈负向选择**的变异与产量调整后的蛋白质含量下降显著相关（p < 0.01）。
    *   受到**中等至高水平正向选择**的变异与产量增加显著相关（p < 0.01）。
*   **预测性能**：尽管这些变异与性状相关，但将选择信息纳入 GBLUP 模型**并未显著提高**基因组预测的准确性。这可能是由于育种群体中连锁不平衡（LD）较强，标准模型已捕捉了大部分遗传效应。

### 7. 优点
*   **无需表型**：该方法最大的亮点在于可以在育种早期、甚至没有表型数据的情况下，仅通过基因型频率的变化来筛选潜在的优良变异。
*   **补充传统方法**：为 GWAS 提供了一个有力的补充工具，特别是在处理复杂性状和长期育种趋势分析时。
*   **利用历史数据**：充分挖掘了育种计划中积累的时间序列基因型数据。

### 8. 不足与局限
*   **预测增益有限**：在提高基因组预测准确率（Prediction Accuracy）方面表现不佳，限制了其在直接辅助选种（Genomic Selection）中的即时应用。
*   **群体特异性**：推断出的选择信号高度依赖于特定育种计划的选择目标，可能无法直接推广到其他环境或育种群体。
*   **遗传漂变干扰**：虽然模型试图捕捉选择信号，但在小规模育种群体中，随机遗传漂变可能会干扰等位基因频率的趋势，导致假阳性。

（完）
