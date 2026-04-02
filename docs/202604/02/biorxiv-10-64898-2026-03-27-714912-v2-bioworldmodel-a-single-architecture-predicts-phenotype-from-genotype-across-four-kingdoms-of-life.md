---
title: "BioWorldModel: a single architecture predicts phenotype from genotype across four kingdoms of life"
title_zh: BioWorldModel：一个跨越四个生物界的从基因型预测表型的单一架构
authors: "Shaik, K. H. B., Sahu, A."
date: 2026-04-01
pdf: "https://www.biorxiv.org/content/10.64898/2026.03.27.714912v2.full.pdf"
tags: ["query:med-ai"]
score: 10.0
evidence: 跨环境从基因型预测表型的世界模型架构
tldr: BioWorldModel 是一种跨物种的统一架构，通过模拟从基因型到表型生成的动态生物过程（调控、表达、通路、细胞），实现了对细菌、真菌、动物和植物四大界生物表型的高精度预测。该模型利用冻结的基因嵌入和状态调节注意力机制，在多种复杂性状预测任务中显著优于传统回归方法，证明了模拟生物生成过程比单纯的关联分析更具预测力。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-27-714912-v2/fig-001.webp\", \"caption\": \"Figure 2: Comprehensive evaluation across all four kingdoms. (Row A) Point prediction accuracy: BioWorldModel outperforms Ridge (GBLUP) and Random Forest baselines in all organisms. E. coli : mean r = 0.678 (+207% vs ridge); S. cerevisiae: r = 0.915 (+167%); D. melanogaster : r = 0.499 (+760%); O. sativa: r = 0.995 (+49%). (Row B) Calibration quality: Expected calibration error (ECE) varies across organisms. Rice shows excellent calibration (ECE = 0.054), Drosophila moderate (ECE = 0.192), while bacteria and yeast require improvement (ECE > 0.47). Prediction interval coverage plotted against target coverage with perfect calibration shown as diagonal. (Row C) Uncertainty decomposition: Epistemic (model) vs aleatoric (irreducible) uncertainty. Epistemic-error correlation indicates model’s awareness of its limitations: rice r = 0.652, Drosophila r = 0.110, E. coli r = 0.078, yeast r = 0.060. Epistemic/aleatoric ratio shows relative contribution of model uncertainty.\", \"page\": 7, \"index\": 1, \"width\": 904, \"height\": 799}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-27-714912-v2/fig-002.webp\", \"caption\": \"Figure 4: Uncertainty decomposition across all four organisms. (Row A) Epistemic (model) vs aleatoric (irreducible) uncertainty in stacked bars for each organism. Epistemic/aleatoric ratio varies: yeast shows highest ratio (0.777, model-dominated), E. coli lowest (0.235, noisedominated), rice and Drosophila intermediate (0.604 and 0.142 respectively). (Row B) Epistemic uncertainty correlates with prediction error in all organisms, demonstrating model awareness of its limitations. Strongest correlation in rice (r = 0.652), moderate in Drosophila (r = 0.110), weaker in E. coli (r = 0.078) and yeast (r = 0.060). Scatter plots show simulated data with fitted regression lines. High epistemic uncertainty reliably indicates regions where predictions are less trustworthy.\", \"page\": 10, \"index\": 2, \"width\": 905, \"height\": 602}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-27-714912-v2/fig-003.webp\", \"caption\": \"Figure 3: Cross-kingdom performance and generalization. (A) Sample size effects: Performance vs test sample count. Small-sample strength demonstrated in Drosophila (N=41, r=0.499). Saturation approaches in rice (N=83, r=0.995). (B) Trait dimensionality: Performance vs number of traits. High-dimensional regime (E. coli : 214 traits, D. melanogaster : 199 traits) shows biological structure stabilizes learning. (C) Covariance structure recovery: Correlation between predicted and empirical trait covariances. Rice shows strongest recovery (r=0.594), E. coli moderate (r=0.387), suggesting learned pleiotropy structure captures real biology.\", \"page\": 8, \"index\": 3, \"width\": 903, \"height\": 716}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-27-714912-v2/fig-004.webp\", \"caption\": \"Table 3: Extended Data Table 1: Ablation study on E. coli confirms each component contributes.\", \"page\": 19, \"index\": 4, \"width\": 818, \"height\": 361}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-27-714912-v2/fig-005.webp\", \"caption\": \"Table 2: Probabilistic quality varies across organisms.\", \"page\": 9, \"index\": 5, \"width\": 940, \"height\": 226}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-27-714912-v2/fig-006.webp\", \"caption\": \"Table 4: Extended Data Table 2: Comprehensive baseline comparison across all four organisms. We evaluated five classical methods on the same train/test splits. Ridge regression (GBLUP) and Random Forest are shown in main text as representative baselines; BayesB (ElasticNet proxy) and Lasso provide additional benchmarks. All baselines trained per-trait with hyperparameter tuning. BioWorldModel trained once per organism with fixed architecture, predicting all traits jointly.\", \"page\": 20, \"index\": 6, \"width\": 960, \"height\": 860}]"
motivation: 传统模型通常将基因型视为静态编码并独立处理性状，忽略了生物体在不同环境下动态生成表型的复杂生物学机制。
method: 该架构通过调控、表达、通路和细胞四个生物过程层处理基因变异，并利用状态调节注意力机制结合环境与时间因素预测多元性状分布。
result: "模型在细菌、酵母、果蝇和水稻的数百种性状预测中表现卓越，相关性系数最高达0.995，性能较传统回归方法提升了49%至760%不等。"
conclusion: 研究证明，模拟生物学生成表型的动态过程而非仅仅进行统计关联，是捕获复杂生物特征并提升预测准确性的核心。
---

## 摘要
相同的基因组在不同条件下会产生不同的表型，然而目前的预测模型通常只对基因型进行一次编码，并将每个性状视为相互独立。在本文中，我们展示了将表型生成表示为一个动态生物过程，能够彻底改变细菌、真菌、动物和植物的预测准确性。BioWorldModel 学习生物体如何解读其基因组：受个体变异调制的冻结基因嵌入（物种上下文）通过四个生物过程层（从调控到表达，再到通路，最后到细胞层面），这些过程层会对环境和时间做出响应。一种状态条件注意力机制会重新读取这种动态表示，从而预测完整的多元性状分布。在无需修改的情况下，该架构在 214 个细菌生长性状上实现了平均相关系数 r = 0.678（比岭回归提高 207%），在 35 个酵母适应性性状上实现了 r = 0.915（提高 167%），在小样本情形下的 199 个果蝇表型上实现了 r = 0.499（提高 760%），并在 36 个水稻性状上实现了 r = 0.995（提高 49%）。消融实验证实，驱动性能提升的是对生物过程的建模，而非模型规模。当神经架构能够表征生物学如何生成表型，而不仅仅是将基因型与结果相关联时，它们就能捕捉到静态方法所遗漏的信息。

## Abstract
The same genome produces different phenotypes in different conditions--yet predictive models encode genotype once and treat each trait independently. Here we show that representing phenotype generation as a dynamic biological process transforms predictive accuracy across bacteria, fungi, animals and plants. BioWorldModel learns how organisms interpret their genome: frozen gene embeddings (species context) modulated by individual variation pass through four biological process layers (regulation to expression to pathway to cellular) that respond to environment and time. A state-conditioned attention mechanism rereads this dynamic representation, predicting full multivariate trait distributions. Without modification, the architecture achieves mean correlation r = 0.678 on 214 bacterial growth traits (207% better than ridge regression), r = 0.915 on 35 yeast fitness traits (167% better), r = 0.499 on 199 fly phenotypes in small-sample regime (760% better), and r = 0.995 on 36 rice traits (49% better). Ablations confirm that modeling biological process--not model size--drives performance. When neural architectures represent how biology generates phenotype rather than merely associating genotype with outcome, they capture what static methods miss.

---

## 论文详细总结（自动生成）

这是一份关于论文《BioWorldModel: a single architecture predicts phenotype from genotype across four kingdoms of life》的深度结构化总结：

### 1. 核心问题与研究动机
*   **核心问题**：传统的基因组预测方法（如岭回归、随机森林）通常将基因型视为静态编码，并独立处理每个性状，忽略了生物体在不同环境、时间和生理状态下动态“解读”基因组的生物学本质。
*   **研究动机**：相同的基因组在不同条件下会产生不同的表型。作者认为，预测模型不应仅仅是统计上的关联匹配，而应模拟生物体生成表型的动态过程（即从调控到细胞层面的解释过程）。

### 2. 方法论：BioWorldModel 架构
BioWorldModel 采用单一架构，通过模拟生物生成过程来预测多元性状分布。其核心技术包括：
*   **因子化基因表示**：将基因表示分为两部分：
    *   **物种上下文（href）**：使用冻结的 Evo 2 (7B) 大模型嵌入，捕捉进化的功能约束。
    *   **个体变异（δh）**：通过学习个体 SNP 特征（如杂合/纯合计数、剂量等）来调制参考嵌入。
*   **BioProcessStack（生物过程栈）**：包含四个顺序层：**调控 → 表达 → 通路 → 细胞**。每一层都通过环境（$e_t$）和时间（$t$）门控的残差连接进行动态调整。
*   **ReadGate（状态条件读取）**：一种注意力机制，根据当前的生物状态、环境和记忆，从 64 个动态基因组向量中选择性地读取相关信号。
*   **四通道生物记忆**：模拟不同时间尺度的生物反馈：稳态（慢速）、发育（时间门控）、偶发（冲击事件）和群体（物种基准）。
*   **多元输出头**：使用 Cholesky 参数化预测完整的性状协方差矩阵，从而捕捉多效性（一个基因影响多个性状）。

### 3. 实验设计与基准对比
*   **数据集**：涵盖生命四大界：
    *   **细菌 (*E. coli*)**：678 个菌株，214 个生长性状。
    *   **真菌 (*S. cerevisiae*)**：971 个分离株，35 个适应性性状。
    *   **动物 (*D. melanogaster*)**：205 个品系，199 个形态/行为性状（小样本挑战）。
    *   **植物 (*O. sativa*)**：413 个品种，36 个农艺性状。
*   **对比基准 (Benchmarks)**：
    *   岭回归 (GBLUP)
    *   随机森林 (Random Forest)
    *   BayesB (ElasticNet)
    *   Lasso
*   **实验设置**：所有生物使用完全相同的架构和超参数，基准模型则针对每个性状独立训练并进行超参数调优。

### 4. 资源与算力
*   **硬件**：使用了 **4 × NVIDIA H100 (80GB) GPU**。
*   **训练时长**：
    *   细菌：12 小时（500 步）。
    *   酵母：2 天（2000 步）。
    *   果蝇：3 小时（100 步，早停）。
    *   水稻：4 天（1000 步）。
*   **框架**：基于 JAX 和 Haiku 实现。

### 5. 实验数量与充分性
*   **实验规模**：论文在 4 个物种、共计 484 个性状上进行了测试。
*   **消融实验**：设计了 5 组消融实验（在 *E. coli* 上），分别验证了生物过程栈、ReadGate、协方差预测、Evo 2 嵌入以及模型规模的影响。
*   **充分性评价**：实验设计非常充分且客观。通过跨越进化距离极大的四个界，证明了架构的普适性；通过固定超参数与精调基准模型的对比，确保了实验的公平性。

### 6. 主要结论与发现
*   **性能飞跃**：BioWorldModel 在所有物种上均显著优于传统方法。在果蝇（小样本）上提升高达 **760%**，在细菌上提升 **207%**，在水稻上接近饱和（r=0.995）。
*   **结构胜过规模**：消融实验证明，性能提升主要源于对生物过程的建模（如 BioProcessStack 贡献了 23% 的性能），而非单纯增加参数量。
*   **捕捉多效性**：模型能够成功恢复性状间的协方差结构（如水稻中相关性达 0.59），这是独立预测性状的传统方法无法做到的。
*   **不确定性感知**：模型提供的认识不确定性（Epistemic Uncertainty）与预测误差呈正相关，表明模型具有一定的“自知之明”。

### 7. 优点与亮点
*   **统一性**：用同一个架构解决了跨物种、跨性状的预测问题，具有极强的泛化潜力。
*   **生物学可解释性**：架构设计紧贴生物学中心法则和调控逻辑，而非黑盒拟合。
*   **小样本鲁棒性**：在样本量极小（N=41）的果蝇数据集上依然表现稳健，显示了生物学先验知识在数据稀缺时的补偿作用。

### 8. 不足与局限
*   **校准不均**：模型在不同物种上的概率校准表现不一（酵母过自信，细菌欠自信）， distributional 层的成熟度仍需提高。
*   **动态数据缺失**：虽然架构支持时间序列预测，但目前测试的数据集多为静态快照，尚未充分验证其在纵向发育数据上的表现。
*   **跨群体迁移待证**：虽然跨物种表现优异，但在同一物种不同育种群体间的“零样本”迁移能力尚在研究中。

（完）
