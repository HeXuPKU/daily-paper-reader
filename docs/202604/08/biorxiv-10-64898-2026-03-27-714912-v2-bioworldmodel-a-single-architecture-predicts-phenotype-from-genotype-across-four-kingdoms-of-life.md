---
title: "BioWorldModel: a single architecture predicts phenotype from genotype across four kingdoms of life"
title_zh: BioWorldModel：一种跨越四个生物界的从基因型预测表型的统一架构
authors: "Shaik, K. H. B., Sahu, A."
date: 2026-04-01
pdf: "https://www.biorxiv.org/content/10.64898/2026.03.27.714912v2.full.pdf"
tags: ["query:med-ai"]
score: 9.0
evidence: 跨物种从基因型预测表型的世界模型架构
tldr: BioWorldModel 是一种跨物种的统一架构，通过模拟生物过程（调控、表达、通路、细胞）将基因型映射为表型。它利用冻结的基因嵌入和动态生物层，结合环境与时间因素，在细菌、真菌、动物和植物四大界中均表现出远超传统方法的预测准确率，证明了模拟生物生成过程比单纯的关联分析更有效。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-27-714912-v2/fig-001.webp\", \"caption\": \"Figure 2: Comprehensive evaluation across all four kingdoms. (Row A) Point prediction accuracy: BioWorldModel outperforms Ridge (GBLUP) and Random Forest baselines in all organisms. E. coli : mean r = 0.678 (+207% vs ridge); S. cerevisiae: r = 0.915 (+167%); D. melanogaster : r = 0.499 (+760%); O. sativa: r = 0.995 (+49%). (Row B) Calibration quality: Expected calibration error (ECE) varies across organisms. Rice shows excellent calibration (ECE = 0.054), Drosophila moderate (ECE = 0.192), while bacteria and yeast require improvement (ECE > 0.47). Prediction interval coverage plotted against target coverage with perfect calibration shown as diagonal. (Row C) Uncertainty decomposition: Epistemic (model) vs aleatoric (irreducible) uncertainty. Epistemic-error correlation indicates model’s awareness of its limitations: rice r = 0.652, Drosophila r = 0.110, E. coli r = 0.078, yeast r = 0.060. Epistemic/aleatoric ratio shows relative contribution of model uncertainty.\", \"page\": 7, \"index\": 1, \"width\": 904, \"height\": 799}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-27-714912-v2/fig-002.webp\", \"caption\": \"Figure 4: Uncertainty decomposition across all four organisms. (Row A) Epistemic (model) vs aleatoric (irreducible) uncertainty in stacked bars for each organism. Epistemic/aleatoric ratio varies: yeast shows highest ratio (0.777, model-dominated), E. coli lowest (0.235, noisedominated), rice and Drosophila intermediate (0.604 and 0.142 respectively). (Row B) Epistemic uncertainty correlates with prediction error in all organisms, demonstrating model awareness of its limitations. Strongest correlation in rice (r = 0.652), moderate in Drosophila (r = 0.110), weaker in E. coli (r = 0.078) and yeast (r = 0.060). Scatter plots show simulated data with fitted regression lines. High epistemic uncertainty reliably indicates regions where predictions are less trustworthy.\", \"page\": 10, \"index\": 2, \"width\": 905, \"height\": 602}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-27-714912-v2/fig-003.webp\", \"caption\": \"Figure 3: Cross-kingdom performance and generalization. (A) Sample size effects: Performance vs test sample count. Small-sample strength demonstrated in Drosophila (N=41, r=0.499). Saturation approaches in rice (N=83, r=0.995). (B) Trait dimensionality: Performance vs number of traits. High-dimensional regime (E. coli : 214 traits, D. melanogaster : 199 traits) shows biological structure stabilizes learning. (C) Covariance structure recovery: Correlation between predicted and empirical trait covariances. Rice shows strongest recovery (r=0.594), E. coli moderate (r=0.387), suggesting learned pleiotropy structure captures real biology.\", \"page\": 8, \"index\": 3, \"width\": 903, \"height\": 716}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-27-714912-v2/fig-004.webp\", \"caption\": \"Table 3: Extended Data Table 1: Ablation study on E. coli confirms each component contributes.\", \"page\": 19, \"index\": 4, \"width\": 818, \"height\": 361}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-27-714912-v2/fig-005.webp\", \"caption\": \"Table 2: Probabilistic quality varies across organisms.\", \"page\": 9, \"index\": 5, \"width\": 940, \"height\": 226}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-27-714912-v2/fig-006.webp\", \"caption\": \"Table 4: Extended Data Table 2: Comprehensive baseline comparison across all four organisms. We evaluated five classical methods on the same train/test splits. Ridge regression (GBLUP) and Random Forest are shown in main text as representative baselines; BayesB (ElasticNet proxy) and Lasso provide additional benchmarks. All baselines trained per-trait with hyperparameter tuning. BioWorldModel trained once per organism with fixed architecture, predicting all traits jointly.\", \"page\": 20, \"index\": 6, \"width\": 960, \"height\": 860}]"
motivation: 传统模型通常将基因型视为静态特征并独立处理性状，忽略了生物体在不同环境下动态生成表型的复杂生物学机制。
method: 该模型通过四个生物过程层（调控、表达、通路、细胞）处理受变异调控的基因嵌入，并利用状态条件注意力机制整合环境与时间信息。
result: "在细菌、酵母、果蝇和水稻的数百种表型预测中，该模型表现显著优于岭回归等传统方法，相关性提升最高达 760%。"
conclusion: 研究证明，模拟生物生成表型的内在逻辑而非简单的统计关联，是提升基因型到表型预测准确性的核心驱动力。
---

## 摘要
同一基因组在不同条件下会产生不同的表型——然而，目前的预测模型通常只对基因型进行一次编码，并将每个性状独立对待。在本文中，我们展示了将表型生成表示为一个动态生物过程，能够显著提升细菌、真菌、动物和植物的预测准确性。BioWorldModel 学习生物体如何解读其基因组：由个体变异调制的冻结基因嵌入（物种上下文）通过四个响应环境和时间的生物过程层（调控 [->] 表达 [->] 通路 [->] 细胞）。一种状态条件注意力机制重新读取这种动态表示，从而预测完整的多元性状分布。在无需修改的情况下，该架构在 214 个细菌生长性状上实现了平均相关系数 r = 0.678（比岭回归提高 207%），在 35 个酵母适应性性状上 r = 0.915（提高 167%），在小样本情况下的 199 个果蝇表型上 r = 0.499（提高 760%），以及在 36 个水稻性状上 r = 0.995（提高 49%）。消融实验证实，驱动性能提升的是对生物过程的建模，而非模型规模。当神经架构能够表征生物学如何生成表型，而不仅仅是将基因型与结果相关联时，它们就能捕捉到静态方法所遗漏的信息。

## Abstract
The same genome produces different phenotypes in different conditions--yet predictive models encode genotype once and treat each trait independently. Here we show that representing phenotype generation as a dynamic biological process transforms predictive accuracy across bacteria, fungi, animals and plants.

BioWorldModel learns how organisms interpret their genome: frozen gene embeddings (species context) modulated by individual variation pass through four biological process layers (regulation [-&gt;] expression [-&gt;] pathway [-&gt;] cellular) that respond to environment and time. A state-conditioned attention mechanism rereads this dynamic representation, predicting full multivariate trait distributions.

Without modification, the architecture achieves mean correlation r = 0.678 on 214 bacterial growth traits (207% better than ridge regression), r = 0.915 on 35 yeast fitness traits (167% better), r = 0.499 on 199 fly phenotypes in small-sample regime (760% better), and r = 0.995 on 36 rice traits (49% better). Ablations confirm that modeling biological process--not model size--drives performance. When neural architectures represent how biology generates phenotype rather than merely associating genotype with outcome, they capture what static methods miss.

---

## 论文详细总结（自动生成）

### BioWorldModel 论文深度总结

#### 1. 核心问题与整体含义（研究动机和背景）
传统的基因组预测（Genomic Prediction）方法（如岭回归、随机森林）通常将基因型视为静态特征，并假设基因型与表型之间存在直接的统计关联。然而，生物学现实是：**相同的基因组在不同环境和发育阶段会产生截然不同的表型**。基因组并非被简单“解码”，而是根据上下文被“解读”的。
本研究的动机在于打破“一个性状一个模型”的静态预测范式，提出一种能够模拟生物体如何根据环境和时间动态解读基因组的统一神经架构——**BioWorldModel**。其核心目标是证明：**模拟生物生成过程（Process Modeling）比单纯的统计关联（Pattern Matching）更具预测力和泛化性。**

#### 2. 方法论：核心思想与技术细节
BioWorldModel 采用单一架构，通过四个关键创新模拟生物学过程：
*   **因子化基因表示**：将基因表示分为两部分：一是来自大规模预训练模型（Evo 2 7B）的**冻结物种上下文嵌入**（代表基因的功能本质），二是由个体 SNP 特征驱动的**学习变异调制**。
*   **BioProcessStack（生物过程栈）**：设计了四个顺序层——**调控（Regulation）→ 表达（Expression）→ 通路（Pathway）→ 细胞（Cellular）**。每一层都通过环境和时间信号进行门控调制，模拟基因表达的条件性。
*   **ReadGate（状态条件读取）**：引入注意力机制，根据生物体当前的内部状态、环境和记忆，从基因组表示中选择性地读取相关信息。
*   **四通道生物记忆**：模拟生物体整合信息的不同时间尺度，包括稳态（Homeostatic）、发育（Developmental）、偶发（Episodic）和群体（Population）记忆。
*   **多元输出头**：使用 Cholesky 参数化预测完整的性状协方差矩阵，从而捕捉**基因多效性**（Pleiotropy，即一个基因影响多个性状）。

#### 3. 实验设计：数据集、Benchmark 与对比方法
研究在跨越生命四大界的四个数据集上进行了验证，且**架构和超参数完全固定**：
*   **细菌（大肠杆菌）**：214 个生长适应性性状。
*   **真菌（酿酒酵母）**：35 个适应性性状。
*   **动物（黑腹果蝇）**：199 个形态、行为和生活史性状（处于极小样本制度，N=41）。
*   **植物（水稻）**：36 个农艺性状。
*   **Benchmark（基准方法）**：包括岭回归（GBLUP）、随机森林（Random Forest）、BayesB（ElasticNet 代理）和 Lasso。所有基准方法均针对每个性状独立训练并进行了充分的超参数调优。

#### 4. 资源与算力
*   **硬件**：使用了 4 张 NVIDIA H100 GPU (80GB)。
*   **框架**：基于 JAX 和 Haiku 构建。
*   **训练时长**：
    *   大肠杆菌：12 小时（500 步）。
    *   酵母：2 天（2000 步）。
    *   果蝇：3 小时（100 步，早停）。
    *   水稻：4 天（1000 步）。
*   **推理**：在 CPU 上每人每步约 1-3 秒。

#### 5. 实验数量与充分性
实验设计非常充分且具有说服力：
*   **跨物种验证**：在四个进化距离极远的物种上取得了一致的领先，证明了架构的普适性。
*   **消融实验**：在细菌数据集上进行了 5 组消融实验，分别验证了生物过程层（下降 23%）、ReadGate（下降 13%）、多元协方差输出以及 Evo 2 嵌入（下降 25%）的贡献。
*   **客观性**：作者强调在所有物种中使用相同的超参数，避免了针对特定数据集的过拟合（Cherry-picking），这在深度学习研究中尤为难得。

#### 6. 主要结论与发现
*   **性能飞跃**：BioWorldModel 在所有物种中均显著优于传统方法。在果蝇的小样本任务中，相关性提升高达 **760%**；在水稻任务中，相关性接近饱和（r=0.995）。
*   **结构胜过规模**：消融实验证明，性能提升源于对生物过程的显式建模，而非简单的参数堆叠。
*   **捕捉多效性**：模型能够成功恢复性状间的协方差结构（如水稻中 r=0.59），这是独立预测性状的传统方法无法做到的。
*   **不确定性感知**：模型产生的认识不确定性（Epistemic Uncertainty）与预测误差呈正相关，表明模型具有一定的“自知之明”。

#### 7. 优点：亮点总结
*   **生物学启发式设计**：将“基因组解读”这一生物学直觉转化为可计算的神经模块（如 BioProcessStack）。
*   **小样本鲁棒性**：在数据极度匮乏（如果蝇数据集）的情况下，生物学先验结构起到了强大的正则化作用，防止了模型崩溃。
*   **统一性**：打破了物种间的壁垒，展示了生命科学领域“大模型”的可能性。
*   **概率化输出**：不仅给出点预测，还提供完整的分布和不确定性估计。

#### 8. 不足与局限
*   **校准度不均**：虽然在水稻上校准良好，但在酵母上表现出过自信（Overconfidence），在细菌上则欠自信，表明概率层的训练仍需优化。
*   **时序动态未充分测试**：虽然架构包含循环神经网络（GRU）和记忆通道，但目前测试的数据集多为静态快照，尚未在真正的长时序纵向数据上验证。
*   **跨群体迁移风险**：目前主要报告的是物种内性能，跨地理群体或跨育种计划的“零样本”迁移能力仍有待进一步实验证明。
*   **计算成本**：相比于秒级训练的岭回归，该模型需要昂贵的 GPU 资源和数天的训练时间。

（完）
