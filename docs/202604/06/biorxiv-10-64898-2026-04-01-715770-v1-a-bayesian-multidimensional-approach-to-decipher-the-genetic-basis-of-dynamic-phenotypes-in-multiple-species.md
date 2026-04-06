---
title: A Bayesian multidimensional approach to decipher the genetic basis of dynamic phenotypes in multiple species
title_zh: 一种用于解析多物种动态表型遗传基础的贝叶斯多维方法
authors: "Blois, L., Heuclin, B., Bernard, A., Denis, M., Dirlewanger, E., Foulongne-Oriol, M., Marullo, P., Peltier, E., Quero-Garcia, J., Marguerit, E., Gion, J.-M."
date: 2026-04-03
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.01.715770v1.full.pdf"
tags: ["query:gwas"]
score: 9.0
evidence: 用于分析复杂表型遗传结构的贝叶斯框架
tldr: 本研究针对复杂性状随时间变化的遗传机制，提出了一种多变量贝叶斯框架——贝叶斯变系数模型（BVCM）。该方法通过多位点分析，在酵母、真菌、桉树和甜樱桃等多种生物的动态表型数据中进行了验证。相比传统逐时间点关联分析，BVCM能更有效地识别主效及微效QTL，揭示性状随时间变化的动态遗传结构，显著提高了表型变异的解释率，为功能基因组学和育种提供了新工具。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-01-715770-v1/fig-001.webp\", \"caption\": \"\", \"page\": 10, \"index\": 1, \"width\": 1378, \"height\": 1378}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-01-715770-v1/fig-002.webp\", \"caption\": \"\", \"page\": 11, \"index\": 2, \"width\": 1377, \"height\": 589}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-01-715770-v1/fig-003.webp\", \"caption\": \"\", \"page\": 12, \"index\": 3, \"width\": 1377, \"height\": 589}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-01-715770-v1/fig-004.webp\", \"caption\": \"\", \"page\": 14, \"index\": 4, \"width\": 1378, \"height\": 1378}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-01-715770-v1/fig-005.webp\", \"caption\": \"\", \"page\": 15, \"index\": 5, \"width\": 1135, \"height\": 853}]"
motivation: 传统的定量遗传学研究往往忽视了表型随时间变化的动态可塑性及其复杂的遗传基础。
method: 提出并应用了贝叶斯变系数模型（BVCM），这是一种能够同时处理时间和遗传多变量结构的统计框架。
result: BVCM在多种生物中成功检测到主效及微效动态QTL，并比传统方法解释了更多的表型变异。
conclusion: 该研究通过整合时间维度信息，有效缓解了“遗传力缺失”问题，为理解和预测复杂性状的动态演化奠定了基础。
---

## 摘要
解析复杂数量表型的遗传结构在数量遗传学中仍然具有挑战性。这些性状不仅取决于多个遗传因素，而且是随时间和环境而建立的。尽管数量遗传学已经研究了在对比环境条件下表型可塑性的遗传决定因素，但与时间相关的表型可塑性受到的关注较少。在此，我们提出了一种多元贝叶斯框架，即贝叶斯变系数模型（BVCM），旨在通过多位点方法分析时间相关表型可塑性的遗传结构。我们将 BVCM 应用于在多种生物物种中以不同时间尺度（日、月、年）测量的序列时间表型。本研究涵盖的物种包括：酵母（Saccharomyces cerevisiae）、真菌（Fusarium graminearum）、桉树（Eucalyptus urophylla x E. grandis）和甜樱桃树（Prunus avium）。我们将 BVCM 的结果与通过已知的逐时间点进行的全基因组关联分析方法获得的结果进行了比较。对于所有物种和性状，BVCM 均能检测到标记-性状关联方法识别的主要 QTL，并揭示了额外的微效遗传区域。此外，它还提高了大多数所研究表型的表型方差解释率。该模型揭示了随时间具有瞬时、增加或减少效应的动态 QTL。通过在单一统计模型中同时考虑时间与遗传的多元结构，我们增强了对复杂性状遗传结构的理解，特别是显著缓解了遗传力缺失的问题。更广泛地说，这项工作为功能基因组学、进化生态学和作物育种计划中的扩展应用奠定了基础，在这些领域中，时间相关的表型可塑性对于预测和选择关键的数量复杂性状至关重要。

## Abstract
Deciphering the genetic architecture of complex quantitative phenotypes remains challenging in quantitative genetics. These traits not only depend of multiple genetic factors but are also established over time and environments. Although quantitative genetics has investigated the genetic determinism of phenotypic plasticity in contrasted environmental conditions, the time related phenotypic plasticity has received less attention. Here we proposed a multivariate Bayesian framework, the Bayesian Varying Coefficient Model, designed for analysing the genetic architecture of the time related phenotypic plasticity by a multilocus approach. We applied the BVCM to time series phenotypes measured at various time scales (daily, monthly, yearly) across a diverse set of biological species. We included in this study: yeast (Saccharomyces cerevisiae), fungi (Fusarium graminearum), eucalyptus (Eucalyptus urophylla x E. grandis), and sweet cherry tree (Prunus avium). The BVCM results were compared with those obtained with a known genome-wide association method carried out time by time. For all species and traits, the BVCM was able to detect the major QTL identified by marker-trait association methods and revealed additional genetic regions of weak effect. It also increased the phenotypic variance explained for most of the phenotypes considered. It revealed dynamic QTLs with transitory, increasing or decreasing effects over time. By considering both the temporal and genetic multivariate structures in a single statistical model, we increased our understanding of the genetic architecture of complex traits notably by reducing the issue of missing heritability. More broadly, this work raises the foundation for extended applications in functional genomics, evolutionary ecology, and crop breeding programs, in which time-related phenotypic plasticity remains crucial for predicting and selecting key quantitative complex traits.

---

## 论文详细总结（自动生成）

这是一份关于论文《A Bayesian multidimensional approach to decipher the genetic basis of dynamic phenotypes in multiple species》的结构化深入总结：

### 1. 核心问题与整体含义
*   **研究背景**：复杂数量性状（如生长、发育、物候）并非静态，而是随时间动态建立的。传统的定量遗传学研究（如QTL定位或GWAS）通常只关注单一时间点，或者对时间序列数据进行逐个时间点的独立分析。
*   **核心问题**：逐时间点分析忽视了数据的时间依赖性，且难以捕捉在整个发育过程中效应微弱或瞬时存在的遗传因素，导致“遗传力缺失（Missing Heritability）”问题。
*   **研究目的**：开发并验证一种能够同时整合“多位点遗传结构”和“时间维度动态变化”的统计框架，以更全面地解析复杂性状的遗传基础。

### 2. 方法论
*   **核心思想**：提出**贝叶斯变系数模型（BVCM）**。该模型将表型视为时间的函数，并将遗传效应建模为随时间变化的系数。
*   **关键技术细节**：
    *   **多元线性框架**：同时处理所有时间点的观测值，利用时间的连续性增强统计效能。
    *   **动态效应估计**：使用 **B-样条（B-splines）** 插值方法来估计标记效应随时间的演变轨迹，减少了需要估计的参数数量。
    *   **变量选择**：采用**钉子-平板先验（Spike-and-Slab prior）**实现贝叶斯收缩，自动识别与性状关联的显著标记。
    *   **两步筛选流程**：
        1.  **初步筛选**：运行100次MCMC链，处理标记间的多重共线性，识别高关联概率的候选区域。
        2.  **精细选择**：在缩减后的标记子集上再次运行MCMC，通过后验边缘概率（0.4或0.8阈值）确定最终QTL。

### 3. 实验设计
*   **数据集与场景**：
    1.  **酵母 (S. cerevisiae)**：分析发酵过程中的CO2释放动态（10个时间点，小时级）。
    2.  **真菌 (F. graminearum)**：分析致病力严重程度和体外生长速度（6-9个时间点，天级）。
    3.  **桉树 (Eucalyptus)**：分析树木胸径生长（8个时间点，月级）。
    4.  **甜樱桃 (P. avium)**：分析多年开花物候（4个年份，年级）。
*   **Benchmark（基准对比）**：
    *   使用 **BLINK** 方法（一种先进的多位点GWAS模型）作为对照，但采取传统的“逐时间点（Time-by-Time）”分析模式。
*   **对比维度**：QTL检出位置、表型方差解释率（PVE）、狭义遗传力（h²）的动态变化。

### 4. 资源与算力
*   **算力说明**：文中**未明确提及**具体的硬件型号（如GPU/CPU核心数）或总训练时长。
*   **计算复杂度迹象**：模型推断依赖 MCMC 算法，文中设定为 10,000 次迭代、20,000 次预热（burn-in）、变薄因子为 5，且第一步需重复 100 次。这表明该方法相比传统线性回归具有更高的计算成本。

### 5. 实验数量与充分性
*   **实验规模**：涵盖了从单细胞生物（酵母）到多年生木本植物（桉树、樱桃）的 4 种不同生物，样本量跨度从 87 到 960 个个体。
*   **充分性评价**：实验设计非常**充分且客观**。通过跨物种、跨时间尺度（小时到年）的验证，证明了 BVCM 的通用性。研究不仅关注主效 QTL，还深入分析了微效 QTL 的动态轨迹，对比实验覆盖了不同遗传力水平的场景。

### 6. 主要结论与发现
*   **检测能力增强**：BVCM 成功检测到了所有由 BLINK 发现的主效 QTL，并额外发现了大量具有微效或瞬时效应的遗传区域。
*   **解释率提升**：BVCM 显著提高了表型变异的解释率（PVE）。在酵母实验中，BVCM 识别的标记簇比 BLINK 多解释了 27.3% 的变异；平均而言，PVE 提升了约 7%。
*   **揭示动态模式**：模型揭示了 QTL 效应的三种动态类型：瞬时效应、随时间增强效应、随时间减弱效应。
*   **缓解遗传力缺失**：通过整合时间维度和多位点信息，BVCM 能够捕捉到在单一时间点被视为“噪声”的微弱遗传信号。

### 7. 优点与亮点
*   **多维整合**：打破了传统 GWAS 将时间点割裂的局限，实现了遗传与时间的联合建模。
*   **灵敏度高**：利用时间序列的累积信息，增强了对微效变异的检测效能。
*   **两步法策略**：有效地解决了高密度标记带来的多重共线性问题，提高了贝叶斯推断的稳定性。
*   **广泛适用性**：证明了该模型在不同生物界（真菌、植物、酵母）和不同表型尺度下的鲁棒性。

### 8. 不足与局限
*   **计算效率**：MCMC 算法在大规模基因组数据（如数百万 SNP）上的计算压力较大，可能限制其在大规模人类 GWAS 中的直接应用。
*   **标记预处理依赖**：为了降低复杂度，模型在运行前过滤了高度相关的标记，这可能导致某些因果变异被代表性标记替代，而非直接定位。
*   **小样本限制**：在样本量较小（如甜樱桃，n=115）且时间点较少的情况下，BVCM 相比传统方法的优势会减弱。
*   **上位性建模**：虽然模型在多变量框架下考虑了标记间的关系，但未显式地对复杂的非加性效应（如上位性）进行量化评估。

（完）
