---
title: Optimizing phenotype scale improves genetic analyses in large-scale biobanks
title_zh: 优化表型尺度可改进大规模生物样本库中的遗传分析
authors: "Huang, Z., Costantino, M., Dahl, A."
date: 2026-05-07
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.04.722531v1.full.pdf"
tags: ["query:gwas"]
score: 9.0
evidence: 用于优化遗传分析中表型尺度的创新算法 SIQReg
tldr: "针对大规模生物样本库中表型测量尺度常被忽视导致遗传分析偏差的问题，本文提出SIQReg方法。该方法通过最小化分位数间的异质性来学习数据驱动的表型尺度。在英国生物样本库的应用表明，SIQReg能有效消除非加性遗传信号中的统计伪影，同时显著提升加性信号的检测效能（如GWAS位点增加11%）和多基因风险评分的预测准确性，为复杂性状的遗传分析提供了更科学的尺度转换方案。"
source: biorxiv
selection_source: fresh_fetch
motivation: 传统的表型测量尺度往往无法准确反映复杂的遗传架构，导致遗传分析中出现统计伪影或效能损失。
method: 开发了SIQReg方法，通过最小化表型分位数之间的异质性，自动学习最优的数据驱动表型转换尺度。
result: "SIQReg消除了绝大部分虚假的非加性信号，同时将GWAS位点检测数和PGS预测准确率分别提升了11%和10%。"
conclusion: SIQReg是一种能够优化表型尺度、提升复杂性状遗传分析准确性和统计效能的原则性方法。
---

## 摘要
大规模生物样本库使得针对数千种表型的日益复杂的遗传分析成为可能。然而，研究很少考虑合适的表型测量尺度，这一问题会极大地影响对遗传架构的推断。在此，我们介绍了 SIQReg，这是针对这一经典问题的一个实用解决方案，它通过最小化表型分位数之间的异质性来学习数据驱动的表型尺度。应用于英国生物样本库（UK Biobank）中的复杂性状时，SIQReg 拒绝了 25 个性状中 24 个的默认尺度。通常，SIQReg 尺度介于默认尺度和对数尺度之间，这表明默认尺度的性状既不是纯加性的，也不是纯乘性的。我们展示了 SIQReg 改进了非加性和加性遗传分析。SIQReg 消除了大部分非加性遗传信号（例如 97% 的 vQTL 和 76% 的分位数依赖型 TWAS 基因），表明它们可能是统计伪影，同时保留了生物学上合理的非加性信号。同时，SIQReg 提高了检测加性信号的效能，使 GWAS 位点、TWAS 基因和 PGS 预测准确性分别增加了 11%、13% 和 10%，并多识别出 50% 的高风险个体。这些收益在不同族裔群体中均得到了验证。我们的结果确立了 SIQReg 作为一种原则性的表型尺度转换方法，能够改进复杂性状的遗传分析。

## Abstract
Large-scale biobanks have enabled increasingly complicated genetic analyses across thousands of phenotypes. However, studies rarely consider the appropriate phenotype measurement scale, a problem that can drastically affect inferences on genetic architecture. Here, we introduce SIQReg, a practical solution to this classical problem, which learns a data-driven phenotype scale by minimizing heterogeneity across phenotype quantiles. Applied to complex traits in UK Biobank, SIQReg rejects the default scale for 24/25 traits. Generally, SIQReg scales lie between default and logarithmic, indicating that default-scale traits are neither purely additive nor purely multiplicative. We show that SIQReg improves both non-additive and additive genetic analyses. SIQReg eliminates most non-additive genetic signals (such as 97% of vQTL and 76% of quantile-dependent TWAS genes), indicating they may be statistical artifacts, while preserving biologically plausible non-additive signals. Simultaneously, SIQReg improves power to detect additive signals, increasing GWAS loci, TWAS genes, and PGS prediction accuracy by 11%, 13%, and 10%, respectively, and identifies 50% more high-risk individuals. These gains replicate across ancestry groups. Our results establish SIQReg as a principled approach to phenotype scale transformation that improves genetic analyses of complex traits.

---

## 论文详细总结（自动生成）

这篇论文介绍了一种名为 **SIQReg**（尺度无关分位数回归）的方法，旨在通过优化表型测量尺度来提升大规模生物样本库中的遗传分析质量。以下是对该论文的深度结构化总结：

### 1. 核心问题与整体含义（研究动机和背景）
*   **研究动机**：在全基因组关联研究（GWAS）中，研究者通常直接使用生物样本库提供的默认表型尺度（如原始测量值）。然而，如果遗传效应在某种潜在尺度上是加性的，但在观测尺度上是非加性的，就会产生“统计伪影”，导致虚假的非加性信号（如 vQTL 或 GxE 交互作用），并降低检测加性遗传效应的统计效能。
*   **核心问题**：如何为特定的复杂性状找到一个最优的数学转换尺度，使得遗传效应在该尺度下表现得最接近纯加性，从而提高分析的准确性和预测能力。

### 2. 方法论：核心思想与技术细节
*   **核心思想**：在正确的表型尺度上，加性遗传效应在表型分布的不同分位数（Quantiles）之间应该是恒定的。SIQReg 通过寻找一个数据驱动的转换参数，使得协变量效应在不同分位数之间的异质性最小化。
*   **关键技术细节**：
    *   **Box-Cox 转换**：采用 Box-Cox 转换家族 $y^* = (y^\lambda - 1)/\lambda$。其中 $\lambda=1$ 为默认尺度，$\lambda=0$ 为对数尺度。
    *   **优化目标**：通过最小化分位数回归系数在不同分位数水平（如 0.1 到 0.9）下的变异（Wald 统计量）来估计最优的 $\lambda$。
    *   **计算优化**：为了处理生物样本库级别的海量数据，使用了“卷积型平滑分位数回归”（conquer）框架，将计算复杂度降低到与样本量成线性关系。
    *   **元分析**：对多个协变量（如年龄、性别、主成分）估计出的 $\lambda$ 进行元分析，以获得稳健的性状特异性尺度。

### 3. 实验设计
*   **数据集**：主要使用英国生物样本库（UK Biobank），涉及约 33.5 万英国白人个体。
*   **验证场景**：在欧洲白人、非洲裔和亚洲裔群体中进行跨族裔验证。
*   **性状范围**：涵盖 25 种复杂性状（如身高、BMI、LDL 胆固醇、睾酮等）。
*   **对比方法（Benchmark）**：
    *   默认尺度（Original Scale）。
    *   对数尺度（Log Scale）。
    *   基于秩的反向正态转换（RINT）。
    *   基于似然的 WarpedLMM 方法。
*   **评估指标**：GWAS 显著位点数、TWAS 关联基因数、多基因风险评分（PGS）的预测准确率（Spearman $R^2$）、高风险个体识别成功率。

### 4. 资源与算力
*   **算力说明**：论文提到使用了芝加哥大学研究计算中心（CRI）维护的 Randi 高性能计算（HPC）集群。
*   **具体细节**：文中未明确列出具体的 GPU 型号、数量或精确的训练时长。但强调了 SIQReg 算法的计算效率，指出其复杂度为 $O(pn)$（$p$ 为系数数量，$n$ 为样本量），适合生物样本库规模的分析。

### 5. 实验数量与充分性
*   **实验规模**：
    *   对 25 个性状进行了全面的尺度估计和下游遗传分析。
    *   进行了大规模模拟实验，验证了在非高斯噪声和异方差情况下的稳健性。
    *   包含了跨族裔（4 个群体）的重复验证。
    *   进行了消融实验，测试了协变量数量对尺度估计稳定性的影响。
*   **充分性评价**：实验设计非常充分且客观。通过模拟和真实数据双重验证，不仅展示了性能提升，还深入探讨了为何某些传统方法（如 RINT）在分位数分析中会失效。

### 6. 主要结论与发现
*   **默认尺度不佳**：在 25 个性状中，有 24 个拒绝了默认尺度。平均而言，最优尺度 $\lambda \approx 0.1$，表明大多数性状更接近对数尺度而非加性尺度。
*   **消除统计伪影**：SIQReg 消除了 97% 的 vQTL 信号和 76% 的异质性 TWAS 信号，证明这些信号大多是尺度选择不当导致的伪影。
*   **提升发现效能**：相比默认尺度，SIQReg 使 GWAS 显著位点增加了 11.2%，TWAS 关联基因增加了 13.2%。
*   **增强预测能力**：PGS 预测准确率平均提升 10.3%，识别出的前 0.1% 高风险个体数量增加了约 50%。

### 7. 优点与亮点
*   **原则性方法**：提供了一个基于分位数恒定性的严谨统计学框架，解决了长达一个世纪的表型尺度选择难题。
*   **数据驱动**：无需预设性状是加性还是乘性，自动学习最优转换。
*   **兼顾发现与预测**：不仅能清理虚假信号，还能显著增强真实遗传信号的检测和风险预测。
*   **稳健性强**：相比 WarpedLMM，SIQReg 对非正态分布的残差具有更强的容忍度。

### 8. 不足与局限
*   **转换家族限制**：目前仅限于单调的 Box-Cox 转换，对于具有复杂边界或非单调分布的表型可能不适用。
*   **连续性假设**：主要针对连续变量设计，尚未扩展到二元（病例/对照）或有序分类变量。
*   **协变量依赖**：尺度估计依赖于协变量的效应，如果协变量本身测量有误或尺度不当，可能会影响结果。
*   **生物学解释**：虽然消除了统计伪影，但某些被消除的“尺度相关异质性”在特定生物学语境下是否仍具意义，仍需进一步探讨。

（完）
