---
title: "BioWorldModel: a single architecture predicts phenotype from genotype across four kingdoms of life"
title_zh: BioWorldModel：一种跨越生物界四大界从基因型预测表型的单一架构
authors: "Shaik, K. H. B., Sahu, A."
date: 2026-04-01
pdf: "https://www.biorxiv.org/content/10.64898/2026.03.27.714912v2.full.pdf"
tags: ["query:med-ai"]
score: 10.0
evidence: 用于跨物种基因型预测表型的世界模型架构
tldr: BioWorldModel是一个跨物种的表型预测框架，通过模拟从基因组到表型的动态生物过程（调控、表达、通路、细胞层级），实现了对细菌、真菌、动物和植物四大界生物性状的高精度预测。该模型整合了基因变异、环境和时间因素，显著优于传统的静态关联方法，证明了模拟生物生成过程在表型预测中的核心价值。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-27-714912-v2/fig-001.webp\", \"caption\": \"Figure 2: Comprehensive evaluation across all four kingdoms. (Row A) Point prediction accuracy: BioWorldModel outperforms Ridge (GBLUP) and Random Forest baselines in all organisms. E. coli : mean r = 0.678 (+207% vs ridge); S. cerevisiae: r = 0.915 (+167%); D. melanogaster : r = 0.499 (+760%); O. sativa: r = 0.995 (+49%). (Row B) Calibration quality: Expected calibration error (ECE) varies across organisms. Rice shows excellent calibration (ECE = 0.054), Drosophila moderate (ECE = 0.192), while bacteria and yeast require improvement (ECE > 0.47). Prediction interval coverage plotted against target coverage with perfect calibration shown as diagonal. (Row C) Uncertainty decomposition: Epistemic (model) vs aleatoric (irreducible) uncertainty. Epistemic-error correlation indicates model’s awareness of its limitations: rice r = 0.652, Drosophila r = 0.110, E. coli r = 0.078, yeast r = 0.060. Epistemic/aleatoric ratio shows relative contribution of model uncertainty.\", \"page\": 7, \"index\": 1, \"width\": 904, \"height\": 799}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-27-714912-v2/fig-002.webp\", \"caption\": \"Figure 4: Uncertainty decomposition across all four organisms. (Row A) Epistemic (model) vs aleatoric (irreducible) uncertainty in stacked bars for each organism. Epistemic/aleatoric ratio varies: yeast shows highest ratio (0.777, model-dominated), E. coli lowest (0.235, noisedominated), rice and Drosophila intermediate (0.604 and 0.142 respectively). (Row B) Epistemic uncertainty correlates with prediction error in all organisms, demonstrating model awareness of its limitations. Strongest correlation in rice (r = 0.652), moderate in Drosophila (r = 0.110), weaker in E. coli (r = 0.078) and yeast (r = 0.060). Scatter plots show simulated data with fitted regression lines. High epistemic uncertainty reliably indicates regions where predictions are less trustworthy.\", \"page\": 10, \"index\": 2, \"width\": 905, \"height\": 602}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-27-714912-v2/fig-003.webp\", \"caption\": \"Figure 3: Cross-kingdom performance and generalization. (A) Sample size effects: Performance vs test sample count. Small-sample strength demonstrated in Drosophila (N=41, r=0.499). Saturation approaches in rice (N=83, r=0.995). (B) Trait dimensionality: Performance vs number of traits. High-dimensional regime (E. coli : 214 traits, D. melanogaster : 199 traits) shows biological structure stabilizes learning. (C) Covariance structure recovery: Correlation between predicted and empirical trait covariances. Rice shows strongest recovery (r=0.594), E. coli moderate (r=0.387), suggesting learned pleiotropy structure captures real biology.\", \"page\": 8, \"index\": 3, \"width\": 903, \"height\": 716}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-27-714912-v2/fig-004.webp\", \"caption\": \"Table 3: Extended Data Table 1: Ablation study on E. coli confirms each component contributes.\", \"page\": 19, \"index\": 4, \"width\": 818, \"height\": 361}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-27-714912-v2/fig-005.webp\", \"caption\": \"Table 2: Probabilistic quality varies across organisms.\", \"page\": 9, \"index\": 5, \"width\": 940, \"height\": 226}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-27-714912-v2/fig-006.webp\", \"caption\": \"Table 4: Extended Data Table 2: Comprehensive baseline comparison across all four organisms. We evaluated five classical methods on the same train/test splits. Ridge regression (GBLUP) and Random Forest are shown in main text as representative baselines; BayesB (ElasticNet proxy) and Lasso provide additional benchmarks. All baselines trained per-trait with hyperparameter tuning. BioWorldModel trained once per organism with fixed architecture, predicting all traits jointly.\", \"page\": 20, \"index\": 6, \"width\": 960, \"height\": 860}]"
motivation: 传统模型通常将基因型与性状进行静态关联，忽略了环境影响以及生物体从基因到表型的复杂动态生成过程。
method: 提出一种包含调控、表达、通路和细胞四个生物过程层的架构，利用状态条件注意力机制处理动态表征以预测多元性状分布。
result: "在细菌、酵母、果蝇和水稻的数百种性状预测中，该模型表现均大幅优于传统方法，预测相关性最高提升了760%。"
conclusion: 研究证明，模拟生物学产生表型的内在逻辑而非仅进行简单的统计关联，是提升基因型到表型预测准确性的关键。
---

## 摘要
相同的基因组在不同条件下会产生不同的表型，然而目前的预测模型通常仅对基因型进行一次编码，并将每个性状视为相互独立。在本文中，我们展示了将表型生成过程表示为一个动态生物过程，可以彻底改变细菌、真菌、动物和植物的预测准确率。BioWorldModel 学习生物体如何解读其基因组：由个体变异调制的冻结基因嵌入（物种上下文）通过四个响应环境和时间的生物过程层（调控 [->] 表达 [->] 通路 [->] 细胞）。一种状态条件注意力机制重新读取这种动态表示，从而预测完整的多元性状分布。在无需修改的情况下，该架构在 214 个细菌生长性状上实现了平均相关系数 r = 0.678（比岭回归提高 207%），在 35 个酵母适应性性状上实现了 r = 0.915（提高 167%），在小样本情况下的 199 个果蝇表型上实现了 r = 0.499（提高 760%），在 36 个水稻性状上实现了 r = 0.995（提高 49%）。消融实验证实，驱动性能提升的是对生物过程的建模，而非模型规模。当神经架构能够表征生物学如何生成表型，而不仅仅是将基因型与结果相关联时，它们就能捕捉到静态方法所遗漏的信息。

## Abstract
The same genome produces different phenotypes in different conditions--yet predictive models encode genotype once and treat each trait independently. Here we show that representing phenotype generation as a dynamic biological process transforms predictive accuracy across bacteria, fungi, animals and plants.

BioWorldModel learns how organisms interpret their genome: frozen gene embeddings (species context) modulated by individual variation pass through four biological process layers (regulation [-&gt;] expression [-&gt;] pathway [-&gt;] cellular) that respond to environment and time. A state-conditioned attention mechanism rereads this dynamic representation, predicting full multivariate trait distributions.

Without modification, the architecture achieves mean correlation r = 0.678 on 214 bacterial growth traits (207% better than ridge regression), r = 0.915 on 35 yeast fitness traits (167% better), r = 0.499 on 199 fly phenotypes in small-sample regime (760% better), and r = 0.995 on 36 rice traits (49% better). Ablations confirm that modeling biological process--not model size--drives performance. When neural architectures represent how biology generates phenotype rather than merely associating genotype with outcome, they capture what static methods miss.

---

## 论文详细总结（自动生成）

### BioWorldModel 论文深度总结

#### 1. 核心问题与研究动机
传统的基因组预测方法（如岭回归、随机森林）通常将基因型视为静态特征，并假设基因型与表型之间是简单的统计关联。然而，生物学本质是动态的：相同的基因组在不同环境、不同发育阶段会产生截然不同的表型。论文的核心动机在于：**与其仅仅寻找基因与性状的“关联”，不如构建一个能够模拟生物体如何“解读”基因组的架构**。研究者旨在通过引入生物过程层级和环境调制机制，提升跨物种（细菌、真菌、动物、植物）的表型预测准确性。

#### 2. 方法论：核心思想与技术细节
BioWorldModel 采用单一架构，通过模拟生物信息流的四个关键环节来实现预测：
*   **基因表征分解**：将基因表示分为“物种上下文”（使用冻结的 Evo 2 7B 基础模型嵌入，捕捉进化约束）和“个体变异”（通过学习 SNP 特征的门控投影来调制参考嵌入）。
*   **BioProcessStack（生物过程栈）**：包含四个功能层（调控 $\rightarrow$ 表达 $\rightarrow$ 通路 $\rightarrow$ 细胞）。每一层都通过环境和时间信号进行门控残差连接，模拟基因在特定条件下的动态表达。
*   **ReadGate（状态条件读取）**：利用注意力机制，根据生物体当前的状态（环境、记忆、循环状态）从基因组表征中选择性地读取相关信息。
*   **四通道生物记忆**：设计了稳态（慢速）、发育（时间门控）、情节（突发冲击）和群体（物种基准）四个记忆通道，捕捉不同时间尺度的生物学效应。
*   **多元输出头**：使用 Cholesky 参数化预测全性状协方差矩阵，从而捕捉多效性（Pleiotropy，即一个基因影响多个性状）。

#### 3. 实验设计
研究在生命世界的四个界中进行了验证：
*   **数据集**：
    *   **细菌 (*E. coli*)**：214 个生长适应性性状，136 个测试样本。
    *   **真菌 (*S. cerevisiae*)**：35 个适应性性状，195 个测试样本。
    *   **动物 (*D. melanogaster*)**：199 个形态、行为和生活史性状，41 个测试样本（极小样本场景）。
    *   **植物 (*O. sativa*)**：36 个农艺性状，83 个测试样本。
*   **Benchmark 与对比方法**：对比了岭回归 (GBLUP)、随机森林 (Random Forest)、BayesB (ElasticNet) 和 Lasso。所有基线模型均针对每个性状独立训练并进行了超参数调优。

#### 4. 资源与算力
*   **硬件**：使用了 **4 × NVIDIA H100 (80GB) GPU**。
*   **软件框架**：基于 JAX 和 Haiku 开发。
*   **训练时长**：因生物体复杂度而异。细菌约 12 小时，酵母约 2 天，果蝇约 3 小时（早停），水稻约 4 天。
*   **推理效率**：在 CPU 上每样本每步推理约 1-3 秒。

#### 5. 实验数量与充分性
*   **实验规模**：涵盖了从 35 到 214 个不等的高维性状，样本量从几十到几百不等，具有广泛的代表性。
*   **消融实验**：在 *E. coli* 数据集上进行了 5 组深入的消融实验，分别验证了生物过程栈、ReadGate、多元输出、基础模型嵌入以及模型整体结构的贡献。
*   **客观性**：模型在四个界使用完全相同的架构和超参数，未针对特定物种调优，证明了其结构的普适性和鲁棒性。

#### 6. 主要结论与发现
*   **性能飞跃**：BioWorldModel 在所有物种上均大幅领先基线。在细菌上提升 207%，酵母提升 167%，果蝇（小样本）提升 760%，水稻提升 49%。
*   **结构胜过规模**：消融实验证明，性能提升主要源于对生物过程的模拟（如环境调制层），而非单纯增加参数量。
*   **捕捉多效性**：模型能够成功恢复性状间的协方差结构（如水稻中相关性达 0.59），这是独立预测性状的传统方法无法做到的。
*   **不确定性感知**：模型生成的认知不确定性（Epistemic Uncertainty）与预测误差呈正相关，表明模型具有一定的“自我认知”能力。

#### 7. 优点
*   **生物学一致性**：架构设计紧贴中心法则和生物调控逻辑，具有很强的可解释性潜力。
*   **跨界通用性**：单一架构通吃四大界，展示了生命系统底层逻辑的统一性。
*   **小样本鲁棒性**：在果蝇实验中，即便样本量极小（N=41），生物学先验结构仍能稳定学习，避免了统计模型的崩溃。

#### 8. 不足与局限
*   **校准度不均**：虽然在水稻上校准良好，但在细菌和酵母上表现出过度自信或自信不足，概率预测的质量仍需优化。
*   **时间动态未充分验证**：虽然架构支持时间序列，但目前测试的数据集多为静态快照，尚未在真正的纵向发育数据上验证记忆通道的威力。
*   **跨群体迁移待证**：目前主要报告了物种内的预测性能，跨地理种群或跨育种计划的“零样本”迁移能力尚在研究中。

（完）
