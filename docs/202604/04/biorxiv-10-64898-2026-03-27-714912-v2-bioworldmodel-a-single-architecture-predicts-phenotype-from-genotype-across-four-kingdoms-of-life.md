---
title: "BioWorldModel: a single architecture predicts phenotype from genotype across four kingdoms of life"
title_zh: BioWorldModel：一种跨越生物界四大界从基因型预测表型的单一架构
authors: "Shaik, K. H. B., Sahu, A."
date: 2026-04-01
pdf: "https://www.biorxiv.org/content/10.64898/2026.03.27.714912v2.full.pdf"
tags: ["query:med-ai"]
score: 9.0
evidence: 使用深度学习架构从基因型预测表型的大规模基因组模型
tldr: BioWorldModel是一个跨物种的表型预测框架，涵盖细菌、真菌、动物和植物四大界。该模型通过模拟生物体解释基因组的动态过程（调控、表达、通路、细胞层级），并结合环境和时间因素，打破了传统模型将基因型与表型静态关联的局限。实验证明，这种模拟生物生成过程的架构在多种生物的数百种性状预测上显著优于传统方法，证明了建模生物学过程而非单纯增加模型规模是提升预测准确性的关键。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-27-714912-v2/fig-001.webp\", \"caption\": \"Figure 2: Comprehensive evaluation across all four kingdoms. (Row A) Point prediction accuracy: BioWorldModel outperforms Ridge (GBLUP) and Random Forest baselines in all organisms. E. coli : mean r = 0.678 (+207% vs ridge); S. cerevisiae: r = 0.915 (+167%); D. melanogaster : r = 0.499 (+760%); O. sativa: r = 0.995 (+49%). (Row B) Calibration quality: Expected calibration error (ECE) varies across organisms. Rice shows excellent calibration (ECE = 0.054), Drosophila moderate (ECE = 0.192), while bacteria and yeast require improvement (ECE > 0.47). Prediction interval coverage plotted against target coverage with perfect calibration shown as diagonal. (Row C) Uncertainty decomposition: Epistemic (model) vs aleatoric (irreducible) uncertainty. Epistemic-error correlation indicates model’s awareness of its limitations: rice r = 0.652, Drosophila r = 0.110, E. coli r = 0.078, yeast r = 0.060. Epistemic/aleatoric ratio shows relative contribution of model uncertainty.\", \"page\": 7, \"index\": 1, \"width\": 904, \"height\": 799}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-27-714912-v2/fig-002.webp\", \"caption\": \"Figure 4: Uncertainty decomposition across all four organisms. (Row A) Epistemic (model) vs aleatoric (irreducible) uncertainty in stacked bars for each organism. Epistemic/aleatoric ratio varies: yeast shows highest ratio (0.777, model-dominated), E. coli lowest (0.235, noisedominated), rice and Drosophila intermediate (0.604 and 0.142 respectively). (Row B) Epistemic uncertainty correlates with prediction error in all organisms, demonstrating model awareness of its limitations. Strongest correlation in rice (r = 0.652), moderate in Drosophila (r = 0.110), weaker in E. coli (r = 0.078) and yeast (r = 0.060). Scatter plots show simulated data with fitted regression lines. High epistemic uncertainty reliably indicates regions where predictions are less trustworthy.\", \"page\": 10, \"index\": 2, \"width\": 905, \"height\": 602}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-27-714912-v2/fig-003.webp\", \"caption\": \"Figure 3: Cross-kingdom performance and generalization. (A) Sample size effects: Performance vs test sample count. Small-sample strength demonstrated in Drosophila (N=41, r=0.499). Saturation approaches in rice (N=83, r=0.995). (B) Trait dimensionality: Performance vs number of traits. High-dimensional regime (E. coli : 214 traits, D. melanogaster : 199 traits) shows biological structure stabilizes learning. (C) Covariance structure recovery: Correlation between predicted and empirical trait covariances. Rice shows strongest recovery (r=0.594), E. coli moderate (r=0.387), suggesting learned pleiotropy structure captures real biology.\", \"page\": 8, \"index\": 3, \"width\": 903, \"height\": 716}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-27-714912-v2/fig-004.webp\", \"caption\": \"Table 3: Extended Data Table 1: Ablation study on E. coli confirms each component contributes.\", \"page\": 19, \"index\": 4, \"width\": 818, \"height\": 361}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-27-714912-v2/fig-005.webp\", \"caption\": \"Table 2: Probabilistic quality varies across organisms.\", \"page\": 9, \"index\": 5, \"width\": 940, \"height\": 226}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-27-714912-v2/fig-006.webp\", \"caption\": \"Table 4: Extended Data Table 2: Comprehensive baseline comparison across all four organisms. We evaluated five classical methods on the same train/test splits. Ridge regression (GBLUP) and Random Forest are shown in main text as representative baselines; BayesB (ElasticNet proxy) and Lasso provide additional benchmarks. All baselines trained per-trait with hyperparameter tuning. BioWorldModel trained once per organism with fixed architecture, predicting all traits jointly.\", \"page\": 20, \"index\": 6, \"width\": 960, \"height\": 860}]"
motivation: 传统预测模型将基因型编码为静态信息且独立处理性状，忽略了生物体在不同环境下动态解释基因组生成表型的复杂过程。
method: 提出一种包含四个生物过程层（调控、表达、通路、细胞）的架构，利用状态条件注意力机制结合环境和时间因素来预测多元性状分布。
result: "在细菌、酵母、果蝇和水稻的数百个性状预测中，该模型表现均大幅优于传统回归方法，最高提升达760%。"
conclusion: 将神经网络架构设计为模拟生物生成表型的过程，而非简单的关联分析，能更有效地捕捉基因型与表型之间的复杂关系。
---

## 摘要
相同的基因组在不同条件下会产生不同的表型，然而现有的预测模型通常仅对基因型进行一次编码，并将每个性状视为相互独立。在本文中，我们展示了将表型生成过程表示为一个动态生物过程，可以显著提升细菌、真菌、动物和植物的预测准确率。BioWorldModel 学习生物体如何解读其基因组：受个体变异调制的冻结基因嵌入（物种上下文）通过四个响应环境和时间的生物过程层（调控 [->] 表达 [->] 通路 [->] 细胞）。一种状态条件注意力机制重新读取这种动态表示，从而预测完整的多元性状分布。在无需修改的情况下，该架构在 214 个细菌生长性状上实现了平均相关系数 r = 0.678（比岭回归提升 207%），在 35 个酵母适应性性状上实现了 r = 0.915（提升 167%），在小样本情况下的 199 个果蝇表型上实现了 r = 0.499（提升 760%），在 36 个水稻性状上实现了 r = 0.995（提升 49%）。消融实验证实，驱动性能提升的是对生物过程的建模，而非模型规模。当神经架构能够表征生物学如何生成表型，而不仅仅是将基因型与结果相关联时，它们就能捕捉到静态方法所遗漏的信息。

## Abstract
The same genome produces different phenotypes in different conditions--yet predictive models encode genotype once and treat each trait independently. Here we show that representing phenotype generation as a dynamic biological process transforms predictive accuracy across bacteria, fungi, animals and plants.

BioWorldModel learns how organisms interpret their genome: frozen gene embeddings (species context) modulated by individual variation pass through four biological process layers (regulation [-&gt;] expression [-&gt;] pathway [-&gt;] cellular) that respond to environment and time. A state-conditioned attention mechanism rereads this dynamic representation, predicting full multivariate trait distributions.

Without modification, the architecture achieves mean correlation r = 0.678 on 214 bacterial growth traits (207% better than ridge regression), r = 0.915 on 35 yeast fitness traits (167% better), r = 0.499 on 199 fly phenotypes in small-sample regime (760% better), and r = 0.995 on 36 rice traits (49% better). Ablations confirm that modeling biological process--not model size--drives performance. When neural architectures represent how biology generates phenotype rather than merely associating genotype with outcome, they capture what static methods miss.

---

## 论文详细总结（自动生成）

### BioWorldModel 论文深度总结

#### 1. 论文的核心问题与整体含义
传统的基因组预测方法（如岭回归、随机森林）通常将基因型视为静态特征，并假设基因型与表型之间是简单的统计关联。然而，生物学本质上是一个动态过程：相同的基因组在不同的环境、发育阶段和生理状态下会被差异化地“解读”。
**研究动机**：论文旨在打破“一个基因型对应一个静态预测值”的局限，提出一种能够模拟生物体如何根据环境和时间动态解释基因组的深度学习架构，从而实现跨越生物四大界（细菌、真菌、动物、植物）的高精度表型预测。

#### 2. 方法论：核心思想与关键技术
BioWorldModel 的核心思想是将表型生成表示为受环境调制的动态生物过程。其架构包含四个关键创新：
*   **因子化基因表示**：将基因表示分为两部分：一是来自预训练基因组基础模型（Evo 2 7B）的**冻结物种上下文嵌入**（代表基因功能）；二是根据个体 SNP 计算的**学习型变异调制**（代表个体差异）。
*   **BioProcessStack（生物过程栈）**：设计了四个显式的生物层级（调控 $\rightarrow$ 表达 $\rightarrow$ 通路 $\rightarrow$ 细胞）。每一层都通过环境和时间信号进行门控调制，使静态基因组转化为动态的分子状态表示。
*   **ReadGate（状态条件读取）**：利用注意力机制，根据生物体当前的生理状态、环境和记忆，动态地从基因组表示中提取相关信息。
*   **四通道生物记忆**：引入了模拟生物特性的记忆机制，包括稳态（长期趋势）、发育（时间门控）、偶发（突发冲击）和群体（物种基准）四个通道。
*   **多元概率输出**：使用 Cholesky 参数化预测完整的性状协方差矩阵，不仅预测均值，还捕捉性状间的多效性（Pleiotropy）和预测不确定性。

#### 3. 实验设计
*   **数据集与场景**：
    *   **细菌（大肠杆菌）**：678 个菌株，214 个生长适应性性状。
    *   **真菌（酿酒酵母）**：971 个分离株，35 个适应性性状。
    *   **动物（黑腹果蝇）**：205 个品系，199 个形态、行为和生活史性状（典型的小样本、高维性状场景）。
    *   **植物（水稻）**：413 个品种，36 个农艺性状。
*   **Benchmark（基准方法）**：对比了基因组最佳线性无偏预测（GBLUP/岭回归）、随机森林（Random Forest）、Lasso、BayesB（ElasticNet 代理）以及均值基准。
*   **对比方式**：所有基准方法针对每个性状独立训练并进行超参数优化；BioWorldModel 则使用统一架构、固定超参数，对每个物种的所有性状进行联合预测。

#### 4. 资源与算力
*   **硬件**：使用了 4 × NVIDIA H100 GPU (80GB)。
*   **软件框架**：基于 JAX 和 Haiku 开发。
*   **训练时长**：
    *   大肠杆菌：12 小时（500 步）。
    *   酵母：2 天（2000 步）。
    *   果蝇：3 小时（100 步，早停）。
    *   水稻：4 天（1000 步）。
*   **推理效率**：单样本单步推理约 1-3 秒（CPU）。

#### 5. 实验数量与充分性
*   **实验规模**：涵盖了生命之树的四个界，涉及数百个性状和数万个遗传标记，实验覆盖面极广。
*   **消融实验**：进行了 5 组关键消融实验（移除生物过程栈、移除 ReadGate、仅使用对角协方差、移除基础模型嵌入等），深入探讨了性能提升的来源。
*   **客观性与公平性**：论文在四个物种上使用了完全相同的模型架构和超参数，未针对特定物种进行微调，这有力地证明了该架构的通用性和鲁棒性。同时，通过不确定性分解（偶然 vs 认知不确定性）和校准度分析（ECE），客观地评价了模型的概率预测质量。

#### 6. 主要结论与发现
*   **性能飞跃**：BioWorldModel 在所有物种上的表现均大幅优于传统方法。在果蝇（小样本）上提升达 760%，在细菌上提升 207%，在水稻上接近饱和预测（r=0.995）。
*   **结构驱动而非规模驱动**：消融实验证明，性能提升主要源于对生物过程的建模（BioProcessStack 贡献最大，约 23%），而非单纯增加参数量。
*   **捕捉多效性**：模型能够成功恢复性状间的协方差结构（如水稻中相关性达 0.59），证明其学习到了真实的生物学关联。
*   **基础模型价值**：引入 Evo 2 的冻结嵌入比直接使用原始 SNP 编码提升了 25% 的性能，显示了进化上下文的重要性。

#### 7. 优点（亮点）
*   **跨界通用性**：单一架构无需修改即可应用于从原核生物到高等真核生物的多种生命形式。
*   **生物学可解释性**：架构设计紧贴中心法则和生物调控逻辑，而非黑箱模型。
*   **小样本鲁棒性**：在样本量极小（N=41）的情况下依然能保持较强的预测能力，这对稀有物种或昂贵实验具有重要意义。
*   **概率化预测**：提供全分布预测和不确定性估计，增强了预测结果的可靠性。

#### 8. 不足与局限
*   **校准度不均**：模型在不同物种上的概率校准表现不一（如酵母预测过于自信，细菌则欠自信），需要进一步优化损失函数或引入温度缩放。
*   **时序动态未充分验证**：虽然架构支持递归状态更新，但目前测试的数据集多为静态快照，尚未在真正的长时序纵向数据上验证其生物记忆通道的效用。
*   **跨群体迁移待证**：目前主要报告了物种内的预测性能，跨地理区域或跨育种群体的“零样本”迁移能力仍处于实验阶段。

（完）
