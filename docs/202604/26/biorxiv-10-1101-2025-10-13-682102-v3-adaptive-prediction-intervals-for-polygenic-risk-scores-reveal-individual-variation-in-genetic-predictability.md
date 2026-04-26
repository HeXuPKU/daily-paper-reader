---
title: Adaptive prediction intervals for polygenic risk scores reveal individual variation in genetic predictability
title_zh: 多基因风险评分的自适应预测区间揭示了遗传可预测性的个体差异
authors: "Wang, C., Wang, F., Bogdan, M., Masala, M., Fiorillo, E., Devoto, M., Cucca, F., Belsky, D., Ionita-Laza, I."
date: 2026-04-24
pdf: "https://www.biorxiv.org/content/10.1101/2025.10.13.682102v3.full.pdf"
tags: ["query:gwas"]
score: 10.0
evidence: 使用分位数回归和符合预测的PRS个体化不确定性量化框架
tldr: 多基因风险评分（PRS）在预测复杂性状时常忽略个体层面的不确定性。本研究提出一种基于分位数回归和符合性预测的框架，为PRS提供具有覆盖率保证的自适应预测区间。通过对UK Biobank等数据的分析，发现预测区间宽度在个体间差异显著，且与年龄、BMI等因素相关，揭示了遗传预测能力的个体差异，为区分遗传与非遗传主导的表型提供了原则性方法。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有的多基因风险评分预测缺乏对个体层面不确定性的量化，难以区分不同个体间遗传预测准确性的差异。
method: 结合分位数回归和符合性预测技术，构建在极少假设下具有覆盖率保证且能随遗传信息变化的自适应个体化预测区间。
result: 在62种性状的测试中，该方法在维持有效覆盖率的同时，揭示了预测区间宽度与年龄、BMI的正相关性，体现了环境因素对遗传预测力的影响。
conclusion: 该框架为PRS提供了可靠的不确定性度量工具，证明了量化个体预测差异对于解释多基因预测结果和优化风险分层至关重要。
---

## 摘要
多基因风险评分 (PRS) 广泛应用于全基因组关联研究 (GWAS) 后的分析，以预测人类、动物和植物的复杂性状，然而这些预测的不确定性很少在个体层面得到量化。在此，我们介绍了一个基于分位数回归和共形预测的个体化不确定性量化框架，能够在最小假设下构建具有保证覆盖率的预测区间。分位数回归实现了自适应的、针对特定个体的预测区间，这些区间能够捕捉非对称性，并允许区间宽度仅根据遗传信息在不同个体之间产生显著变化。通过将该框架应用于 UK Biobank 和 ProgeNIA/SardiNIA 研究中的 62 种性状，我们证明了与现有方法相比，这些区间保持了有效的覆盖率，并由于其自适应构建方式，降低了风险分层中的不确定性。预测区间宽度与年龄和 BMI 呈正相关，表明在遗传效应与环境因素相互作用的人群子集中，遗传可预测性有所降低。我们的研究结果表明，纳入不确定性对于解释多基因预测至关重要，并提供了一种原则性方法，用于区分表型能被遗传预测因子很好解释的个体与非遗传影响占主导地位的个体。

## Abstract
Polygenic risk scores (PRS) are widely used in post-GWAS analyses to predict complex traits across humans, animals, and plants, yet the uncertainty of these predictions is rarely quantified at the individual level. Here, we introduce a framework for individualized uncertainty quantification based on quantile regression and conformal prediction, enabling the construction of prediction intervals with guaranteed coverage under minimal assumptions. Quantile regression enables adaptive, individual-specific prediction intervals that capture asymmetry and allow interval widths to vary substantially across individuals based on genetic information alone. Applying this framework to 62 traits in the UK Biobank and the ProgeNIA/SardiNIA studies, we show that these intervals maintain valid coverage and reduce uncertainty in risk stratification compared to existing methods, driven by their adaptive construction. Prediction interval width correlates positively with age and BMI, indicating reduced genetic predictability in subsets of the population where genetic effects interact with environmental factors. Our results demonstrate that incorporating uncertainty is essential for interpreting polygenic predictions and provide a principled approach to distinguish individuals whose phenotypes are well explained by genetic predictors from those in whom non-genetic influences dominate.

---

## 论文详细总结（自动生成）

这篇论文介绍了一种为多基因风险评分（PRS）提供个体化不确定性量化的新框架。以下是对该研究的深度结构化总结：

### 1. 核心问题与整体含义（研究动机和背景）
*   **核心问题**：多基因风险评分（PRS）通常只提供一个点估计值（预测值），而忽略了预测的不确定性。现有的不确定性衡量方法往往假设所有个体的预测误差是均一的（同方差性），但这忽略了不同个体在遗传可预测性上的差异。
*   **整体含义**：研究旨在解决“如何量化单个个体 PRS 预测的可靠性”这一问题。通过为每个预测值提供一个具有统计保证的“预测区间（PI）”，研究者可以区分哪些人的表型是由遗传主导的（区间窄、可预测性高），哪些人受环境或随机因素影响更大（区间宽、可预测性低）。

### 2. 论文提出的方法论
该框架结合了**分位数回归（Quantile Regression, QR）**和**符合性预测（Conformal Prediction, CP）**：
*   **分位数回归 (QR)**：不同于传统回归预测均值，QR 直接估计目标表型的特定分位数（如第 5% 和第 95% 分位数）。这允许预测区间的宽度根据个体的遗传特征（PRS 或 SNP 数据）自适应地变化，捕捉数据中的异方差性。
*   **符合性预测 (CP)**：这是一种统计推断框架，用于对机器学习模型的输出进行校准。
    *   **流程**：首先在训练集上训练 QR 模型；然后在独立的校准集（Calibration Set）上计算“非一致性得分”（衡量实际观测值偏离分位数预测的程度）；最后根据预设的置信水平（如 90%），调整测试集的预测区间。
*   **关键特性**：该方法在极少假设（无需假设误差服从正态分布）的情况下，能够保证预测区间在总体上具有严格的覆盖率（Coverage Guarantee）。

### 3. 实验设计
*   **数据集**：
    *   **UK Biobank (UKB)**：主要数据集，包含约 40 万欧洲裔个体，涵盖 62 种复杂性状（如身高、BMI、血液指标等）。
    *   **ProgeNIA/SardiNIA**：用于跨队列验证的独立数据集，包含撒丁岛人群的数据。
*   **Benchmark（基准方法）**：
    *   **常数宽度区间**：基于均方根误差（RMSE）构建的固定宽度预测区间（假设所有个体误差相同）。
    *   **标准 PRS 模型**：如 LDpred2 等主流 PRS 构建方法。
*   **对比维度**：覆盖率（实际观测值落在区间内的比例）、区间宽度（效率）、以及区间宽度与年龄、BMI 等协变量的相关性。

### 4. 资源与算力
*   **算力说明**：论文中未详细列出具体的 GPU 型号或训练时长。
*   **推断**：由于 PRS 计算和分位数回归主要涉及大规模线性运算和统计建模，通常在高性能计算集群（HPC）的 CPU 节点上完成。符合性预测步骤计算开销极低，主要压力在于前期大规模 GWAS 数据的预处理和 PRS 权重的训练。

### 5. 实验数量与充分性
*   **实验规模**：研究分析了 **62 种** 不同的连续型性状，这在同类研究中属于非常大规模的验证。
*   **充分性**：
    *   进行了**跨性状验证**，证明了方法在不同遗传力（Heritability）性状下的普适性。
    *   进行了**风险分层分析**，展示了不确定性如何影响高风险人群的识别。
    *   进行了**协变量相关性分析**，探讨了预测不确定性的生物学来源（如年龄、BMI）。
    *   实验设计客观、公平，通过独立的校准集和测试集确保了结果的可靠性。

### 6. 主要结论与发现
*   **个体差异显著**：不同个体的预测区间宽度差异巨大。对于某些性状，最难预测个体的区间宽度可能是最易预测个体的两倍以上。
*   **环境因素的影响**：预测区间宽度与**年龄**和**BMI**呈正相关。这意味着随着年龄增长或 BMI 增加，遗传因素对表型的解释力下降，非遗传因素（环境、生活方式）带来的不确定性增加。
*   **风险分层优化**：传统 PRS 可能会将一些不确定性极高的个体错误地归类为“高风险”。引入预测区间后，可以识别出那些虽然 PRS 分数高但“置信度低”的个体，从而提高临床决策的精准度。

### 7. 优点
*   **统计严谨性**：利用符合性预测提供了理论上的覆盖率保证，不依赖于误差正态分布的强假设。
*   **自适应性**：能够根据个体的遗传背景动态调整区间宽度，揭示了“遗传可预测性”本身也是一种个体特征。
*   **生物学洞察**：不仅是一个数学工具，还揭示了 G×E（基因与环境相互作用）对预测不确定性的贡献。

### 8. 不足与局限
*   **样本量需求**：符合性预测需要一个额外的、足够大的校准集，这在小规模临床研究中可能难以实现。
*   **性状限制**：目前主要针对连续型性状（如身高、生化指标），对于二分类性状（如患病/不患病）的应用尚需进一步扩展。
*   **族裔偏差**：虽然使用了两个队列，但主要集中在欧洲裔人群，该方法在跨族裔迁移时的表现（尤其是当 PRS 权重本身存在偏差时）仍需更多验证。
*   **计算复杂性**：相比于简单的点估计，构建自适应区间需要训练多个分位数模型，增加了计算工作量。

（完）
