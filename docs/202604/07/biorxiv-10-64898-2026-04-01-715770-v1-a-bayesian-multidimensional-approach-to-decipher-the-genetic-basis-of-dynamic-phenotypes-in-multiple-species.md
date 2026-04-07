---
title: A Bayesian multidimensional approach to decipher the genetic basis of dynamic phenotypes in multiple species
title_zh: 一种用于解析多物种动态表型遗传基础的贝叶斯多维方法
authors: "Blois, L., Heuclin, B., Bernard, A., Denis, M., Dirlewanger, E., Foulongne-Oriol, M., Marullo, P., Peltier, E., Quero-Garcia, J., Marguerit, E., Gion, J.-M."
date: 2026-04-03
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.01.715770v1.full.pdf"
tags: ["query:gwas"]
score: 9.0
evidence: 用于分析动态表型遗传结构的多元贝叶斯框架
tldr: 本研究针对复杂性状随时间变化的动态特性，提出了一种多变量贝叶斯框架——贝叶斯变系数模型（BVCM）。该方法通过多位点分析，在酵母、真菌、桉树和甜樱桃等多种生物的跨时间尺度表型数据中进行了验证。BVCM不仅能检测到主要QTL，还能发现微效遗传区域，揭示了QTL效应随时间的动态演变，有效缓解了“遗传力缺失”问题，为功能基因组学和育种提供了新工具。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-01-715770-v1/fig-001.webp\", \"caption\": \"\", \"page\": 10, \"index\": 1, \"width\": 1378, \"height\": 1378}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-01-715770-v1/fig-002.webp\", \"caption\": \"\", \"page\": 11, \"index\": 2, \"width\": 1377, \"height\": 589}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-01-715770-v1/fig-003.webp\", \"caption\": \"\", \"page\": 12, \"index\": 3, \"width\": 1377, \"height\": 589}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-01-715770-v1/fig-004.webp\", \"caption\": \"\", \"page\": 14, \"index\": 4, \"width\": 1378, \"height\": 1378}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-01-715770-v1/fig-005.webp\", \"caption\": \"\", \"page\": 15, \"index\": 5, \"width\": 1135, \"height\": 853}]"
motivation: 传统的定量遗传学研究往往忽略了表型随时间变化的动态可塑性及其复杂的遗传基础。
method: 提出了一种名为贝叶斯变系数模型（BVCM）的多变量贝叶斯框架，用于多位点分析时间相关的表型可塑性。
result: 该模型在多种生物中成功识别出主要及微效QTL，并揭示了遗传效应随时间增强、减弱或暂态变化的动态特征。
conclusion: 通过整合时间和遗传的多变量结构，该方法显著提高了表型变异的解释率，深化了对基因型与表型动态关系的理解。
---

## 摘要
解析复杂数量表型的遗传结构在数量遗传学中仍然具有挑战性。这些性状不仅取决于多个遗传因素，而且是随时间和环境建立的。尽管数量遗传学已经研究了在对比环境条件下表型可塑性的遗传决定因素，但与时间相关的表型可塑性受到的关注较少。在这里，我们提出了一个多变量贝叶斯框架，即贝叶斯变系数模型（BVCM），旨在通过多位点方法分析时间相关表型可塑性的遗传结构。我们将 BVCM 应用于在不同生物物种中以各种时间尺度（日、月、年）测量的序列时间表型。本研究包括：酵母（Saccharomyces cerevisiae）、真菌（Fusarium graminearum）、桉树（Eucalyptus urophylla x E. grandis）和甜樱桃树（Prunus avium）。将 BVCM 的结果与通过逐时间点进行的已知全基因组关联方法获得的结果进行了比较。对于所有物种和性状，BVCM 能够检测到标记-性状关联方法识别的主要 QTL，并揭示了额外的微效遗传区域。它还增加了大多数所考虑表型的表型方差解释率。它揭示了随时间具有瞬时、增加或减少效应的动态 QTL。通过在单个统计模型中同时考虑时间及遗传多变量结构，我们增强了对复杂性状遗传结构的理解，特别是通过减少遗传力缺失问题。更广泛地说，这项工作为功能基因组学、进化生态学和作物育种计划的扩展应用奠定了基础，在这些领域中，时间相关的表型可塑性对于预测和选择关键数量复杂性状至关重要。核心信息：通过捕捉影响时间相关表型可塑性的遗传因素，我们的方法有助于更深入地理解基因型-表型关系的动态本质。

## Abstract
Deciphering the genetic architecture of complex quantitative phenotypes remains challenging in quantitative genetics. These traits not only depend of multiple genetic factors but are also established over time and environments. Although quantitative genetics has investigated the genetic determinism of phenotypic plasticity in contrasted environmental conditions, the time related phenotypic plasticity has received less attention.

Here we proposed a multivariate Bayesian framework, the Bayesian Varying Coefficient Model, designed for analysing the genetic architecture of the time related phenotypic plasticity by a multilocus approach. We applied the BVCM to time series phenotypes measured at various time scales (daily, monthly, yearly) across a diverse set of biological species. We included in this study: yeast (Saccharomyces cerevisiae), fungi (Fusarium graminearum), eucalyptus (Eucalyptus urophylla x E. grandis), and sweet cherry tree (Prunus avium). The BVCM results were compared with those obtained with a known genome-wide association method carried out time by time.

For all species and traits, the BVCM was able to detect the major QTL identified by marker-trait association methods and revealed additional genetic regions of weak effect. It also increased the phenotypic variance explained for most of the phenotypes considered. It revealed dynamic QTLs with transitory, increasing or decreasing effects over time. By considering both the temporal and genetic multivariate structures in a single statistical model, we increased our understanding of the genetic architecture of complex traits notably by reducing the issue of missing heritability. More broadly, this work raises the foundation for extended applications in functional genomics, evolutionary ecology, and crop breeding programs, in which time-related phenotypic plasticity remains crucial for predicting and selecting key quantitative complex traits.

Key messageBy capturing the genetic factors influencing the time related phenotypic plasticity, our approach contributes to a deeper understanding of the dynamic nature of genotype-phenotype relationships.

---

## 论文详细总结（自动生成）

这是一份关于论文《A Bayesian multidimensional approach to decipher the genetic basis of dynamic phenotypes in multiple species》的结构化深入总结：

### 1. 论文的核心问题与整体含义（研究动机和背景）
*   **核心问题**：如何有效解析复杂数量性状随时间变化的动态遗传结构（即“时间相关表型可塑性”）。
*   **研究背景**：大多数定量遗传学研究（如 GWAS）通常只关注单一时间点的表型，或者将时间序列简化为函数参数。然而，生物性状（如生长、发育、物候）是随时间动态建立的，受多个遗传因子在不同阶段的调控。
*   **研究动机**：传统单位点或逐时间点分析方法往往缺乏统计效能，难以捕捉微效遗传效应，导致“遗传力缺失”问题。本文旨在提出一种能够同时整合时间维度和多位点遗传结构的统计框架。

### 2. 论文提出的方法论：核心思想与技术细节
*   **核心思想**：提出**贝叶斯变系数模型（BVCM）**。这是一种多变量贝叶斯框架，通过多位点方法同时分析所有时间点的观测值，估计标记效应随时间的动态演变。
*   **关键技术细节**：
    *   **动态效应估计**：使用 **B-splines（B样条插值）** 来模拟标记效应随时间的连续变化。相比随机游走或 Legendre 多项式，B样条在处理多时间点时参数更少且更简洁。
    *   **变量选择（标记筛选）**：采用 **Spike-and-slab 先验**。该先验能为每个遗传标记计算“后验包含概率”（PIP），从而实现自动化的多位点选择。
    *   **两步优化策略**：
        1.  **第一步**：运行 100 次 MCMC 链进行初步筛选，处理标记间的共线性，识别高关联概率的遗传区域。
        2.  **第二步**：在缩减后的标记子集上再次运行 MCMC，精细估计动态效应并确定最终显著标记。
*   **算法流程**：通过马尔可夫链蒙特卡罗（MCMC）采样进行推断，设置预热期（burn-in）和稀释（thinning）以确保收敛。

### 3. 实验设计
*   **数据集与场景**：涵盖了四个具有代表性的生物系统，体现了极大的生物多样性：
    1.  **酵母 (S. cerevisiae)**：分析发酵过程中的 $CO_2$ 释放（10个时间点，小时级）。
    2.  **真菌 (F. graminearum)**：分析致病力严重程度和体外径向生长（6-9个时间点，天级）。
    3.  **桉树 (Eucalyptus)**：分析树干直径发育（8个时间点，月级）。
    4.  **甜樱桃 (P. avium)**：分析开花物候（4个时间点，年级）。
*   **Benchmark（基准）与对比方法**：
    *   对比了 **BLINK** 方法（一种目前公认的高效多位点 GWAS 算法）。
    *   对比方式：将 BLINK 应用于每个独立的时间点（逐时间点分析），观察其检测到的 QTL 数量及解释的表型方差（PVE）。

### 4. 资源与算力
*   **算力说明**：论文中**未明确提及**具体的硬件型号（如 GPU/CPU）或具体的计算耗时。
*   **计算复杂度迹象**：文中提到 MCMC 算法运行了 10,000 次迭代，预热 20,000 次，稀释因子为 5，且每个步骤重复了 100 次。这种多次重复的贝叶斯采样通常比传统的线性回归（如 BLINK）具有更高的计算成本。

### 5. 实验数量与充分性
*   **实验规模**：针对 4 个物种、6 种不同性状进行了完整分析。样本量从 87（真菌）到 960（桉树）不等，标记密度从 124 个 SNP 到 8,070 个 SNP 不等。
*   **充分性评价**：实验设计非常**充分且客观**。通过跨越微生物、林木、果树等不同生命周期的物种，验证了 BVCM 模型的稳健性和普适性。对比实验不仅关注 QTL 的位置，还深入探讨了表型方差解释率（PVE）随时间的变化，证明了模型在捕捉微效效应方面的优势。

### 6. 论文的主要结论与发现
*   **QTL 检测能力提升**：BVCM 成功检测到了 BLINK 识别的所有主要 QTL，并额外发现了许多具有中微效效应的遗传区域。
*   **表型方差解释率（PVE）增加**：在大多数情况下，BVCM 识别的标记簇比 BLINK 解释了更多的表型变异。例如在酵母数据中，PVE 平均提高了 27.3%。
*   **揭示动态遗传模式**：模型揭示了 QTL 效应的三种动态类型：**瞬时效应**（仅在特定阶段出现）、**递增效应**和**递减效应**。
*   **缓解遗传力缺失**：通过整合时间维度，BVCM 能够利用高遗传力时段的信息来辅助识别低遗传力时段的微弱信号。

### 7. 优点（亮点）
*   **多维整合**：在单一统计模型中同时处理了“时间相关性”和“多位点遗传结构”，避免了多次检验校正带来的效能损失。
*   **灵敏度高**：对微效 QTL 的捕捉能力显著强于逐时间点分析的方法。
*   **两步法创新**：通过两步筛选策略，有效平衡了参数数量与观测值数量之间的矛盾，提高了统计准确性。

### 8. 不足与局限
*   **计算成本**：贝叶斯 MCMC 方法在大规模基因组数据（如数十万标记）上的计算压力可能巨大，文中未讨论其在大数据量下的扩展性。
*   **共线性依赖**：模型在运行前需要对高度相关的标记进行预过滤，这可能导致某些紧密连锁的因果变异被剔除。
*   **低遗传力限制**：在桉树等遗传力本身较低且时间结构不明显的性状中，BVCM 相比传统方法的提升幅度有限。
*   **先验选择**：虽然 B-splines 效果良好，但样条节点的选择和先验参数的设置可能对结果产生一定影响。

（完）
