---
title: "BioWorldModel: a single architecture predicts phenotype from genotype across four kingdoms of life"
title_zh: BioWorldModel：一种跨越生物界四大界从基因型预测表型的单一架构
authors: "Shaik, K. H. B., Sahu, A."
date: 2026-04-01
pdf: "https://www.biorxiv.org/content/10.64898/2026.03.27.714912v2.full.pdf"
tags: ["query:med-ai"]
score: 9.0
evidence: 基因型到表型预测的世界模型架构
tldr: BioWorldModel是一个跨物种的表型预测架构，通过模拟从基因到细胞的四个生物学过程层（调控、表达、通路、细胞），将基因型动态转化为表型。该模型整合了环境和时间变量，在细菌、真菌、动物和植物四大界中均实现了极高的预测精度，证明了模拟生物生成逻辑比单纯的统计关联更具优势。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-27-714912-v2/fig-001.webp\", \"caption\": \"Figure 2: Comprehensive evaluation across all four kingdoms. (Row A) Point prediction accuracy: BioWorldModel outperforms Ridge (GBLUP) and Random Forest baselines in all organisms. E. coli : mean r = 0.678 (+207% vs ridge); S. cerevisiae: r = 0.915 (+167%); D. melanogaster : r = 0.499 (+760%); O. sativa: r = 0.995 (+49%). (Row B) Calibration quality: Expected calibration error (ECE) varies across organisms. Rice shows excellent calibration (ECE = 0.054), Drosophila moderate (ECE = 0.192), while bacteria and yeast require improvement (ECE > 0.47). Prediction interval coverage plotted against target coverage with perfect calibration shown as diagonal. (Row C) Uncertainty decomposition: Epistemic (model) vs aleatoric (irreducible) uncertainty. Epistemic-error correlation indicates model’s awareness of its limitations: rice r = 0.652, Drosophila r = 0.110, E. coli r = 0.078, yeast r = 0.060. Epistemic/aleatoric ratio shows relative contribution of model uncertainty.\", \"page\": 7, \"index\": 1, \"width\": 904, \"height\": 799}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-27-714912-v2/fig-002.webp\", \"caption\": \"Figure 4: Uncertainty decomposition across all four organisms. (Row A) Epistemic (model) vs aleatoric (irreducible) uncertainty in stacked bars for each organism. Epistemic/aleatoric ratio varies: yeast shows highest ratio (0.777, model-dominated), E. coli lowest (0.235, noisedominated), rice and Drosophila intermediate (0.604 and 0.142 respectively). (Row B) Epistemic uncertainty correlates with prediction error in all organisms, demonstrating model awareness of its limitations. Strongest correlation in rice (r = 0.652), moderate in Drosophila (r = 0.110), weaker in E. coli (r = 0.078) and yeast (r = 0.060). Scatter plots show simulated data with fitted regression lines. High epistemic uncertainty reliably indicates regions where predictions are less trustworthy.\", \"page\": 10, \"index\": 2, \"width\": 905, \"height\": 602}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-27-714912-v2/fig-003.webp\", \"caption\": \"Figure 3: Cross-kingdom performance and generalization. (A) Sample size effects: Performance vs test sample count. Small-sample strength demonstrated in Drosophila (N=41, r=0.499). Saturation approaches in rice (N=83, r=0.995). (B) Trait dimensionality: Performance vs number of traits. High-dimensional regime (E. coli : 214 traits, D. melanogaster : 199 traits) shows biological structure stabilizes learning. (C) Covariance structure recovery: Correlation between predicted and empirical trait covariances. Rice shows strongest recovery (r=0.594), E. coli moderate (r=0.387), suggesting learned pleiotropy structure captures real biology.\", \"page\": 8, \"index\": 3, \"width\": 903, \"height\": 716}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-27-714912-v2/fig-004.webp\", \"caption\": \"Table 3: Extended Data Table 1: Ablation study on E. coli confirms each component contributes.\", \"page\": 19, \"index\": 4, \"width\": 818, \"height\": 361}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-27-714912-v2/fig-005.webp\", \"caption\": \"Table 2: Probabilistic quality varies across organisms.\", \"page\": 9, \"index\": 5, \"width\": 940, \"height\": 226}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-27-714912-v2/fig-006.webp\", \"caption\": \"Table 4: Extended Data Table 2: Comprehensive baseline comparison across all four organisms. We evaluated five classical methods on the same train/test splits. Ridge regression (GBLUP) and Random Forest are shown in main text as representative baselines; BayesB (ElasticNet proxy) and Lasso provide additional benchmarks. All baselines trained per-trait with hyperparameter tuning. BioWorldModel trained once per organism with fixed architecture, predicting all traits jointly.\", \"page\": 20, \"index\": 6, \"width\": 960, \"height\": 860}]"
motivation: 传统预测模型通常将基因型与表型视为静态关联，忽略了生物体在不同环境和时间下动态解释基因组的复杂生物过程。
method: 采用冻结的基因嵌入结合个体变异，通过模拟调控、表达、通路和细胞四个生物过程层，并利用状态条件注意力机制预测多元性状。
result: "在细菌、酵母、果蝇和水稻的多种性状预测中，该模型表现显著优于传统方法，相关性提升最高达760%。"
conclusion: 模拟生物生成表型的动态过程而非仅仅学习统计关联，是实现跨物种高精度表型预测的核心驱动力。
---

## 摘要
相同的基因组在不同条件下会产生不同的表型，然而现有的预测模型通常仅对基因型进行一次编码，并将每个性状视为相互独立。在本文中，我们展示了将表型生成表示为一个动态生物过程，可以彻底改变细菌、真菌、动物和植物的预测准确率。BioWorldModel 学习生物体如何解读其基因组：由个体变异调制的冻结基因嵌入（物种背景）通过四个响应环境和时间的生物过程层（调控 [->] 表达 [->] 通路 [->] 细胞）。一种状态条件注意力机制重新读取这种动态表示，从而预测完整的多元性状分布。在无需修改的情况下，该架构在 214 个细菌生长性状上实现了平均相关系数 r = 0.678（比岭回归提高 207%），在 35 个酵母适应性性状上实现了 r = 0.915（提高 167%），在小样本情况下的 199 个果蝇表型上实现了 r = 0.499（提高 760%），在 36 个水稻性状上实现了 r = 0.995（提高 49%）。消融实验证实，驱动性能提升的是对生物过程的建模，而非模型规模。当神经架构能够表征生物学如何生成表型，而不仅仅是将基因型与结果相关联时，它们就能捕捉到静态方法所遗漏的信息。

## Abstract
The same genome produces different phenotypes in different conditions--yet predictive models encode genotype once and treat each trait independently. Here we show that representing phenotype generation as a dynamic biological process transforms predictive accuracy across bacteria, fungi, animals and plants.

BioWorldModel learns how organisms interpret their genome: frozen gene embeddings (species context) modulated by individual variation pass through four biological process layers (regulation [-&gt;] expression [-&gt;] pathway [-&gt;] cellular) that respond to environment and time. A state-conditioned attention mechanism rereads this dynamic representation, predicting full multivariate trait distributions.

Without modification, the architecture achieves mean correlation r = 0.678 on 214 bacterial growth traits (207% better than ridge regression), r = 0.915 on 35 yeast fitness traits (167% better), r = 0.499 on 199 fly phenotypes in small-sample regime (760% better), and r = 0.995 on 36 rice traits (49% better). Ablations confirm that modeling biological process--not model size--drives performance. When neural architectures represent how biology generates phenotype rather than merely associating genotype with outcome, they capture what static methods miss.

---

## 论文详细总结（自动生成）

### BioWorldModel：跨越生物四大界从基因型预测表型的单一架构总结

#### 1. 核心问题与研究动机
传统的基因组预测方法（如岭回归、随机森林）通常将基因型视为静态特征，并独立预测每个性状。然而，生物学本质是动态的：相同的基因组在不同的环境、发育阶段和生理状态下会产生截然不同的表型。
*   **核心问题**：如何构建一个能够模拟生物体“解读”基因组过程的架构，而非仅仅寻找统计关联？
*   **研究动机**：通过引入生物过程层（调控、表达、通路、细胞）和环境调制机制，提升跨物种、跨性状的预测精度，捕捉传统静态方法遗漏的生物学信号。

#### 2. 方法论：核心思想与技术细节
BioWorldModel 采用单一架构，通过以下四个创新点模拟表型生成过程：
*   **基因表示分解**：将基因表示分为“物种背景”和“个体变异”。使用冻结的 **Evo 2 (7B)** 基础模型提取基因嵌入作为物种参考，再通过学习到的门控投影（基于 SNP 特征）进行个体化调制。
*   **BioProcessStack（生物过程栈）**：包含四个顺序层（调控 $\to$ 表达 $\to$ 通路 $\to$ 细胞）。每一层都通过环境和时间信号进行门控残差调制，模拟基因组在特定条件下的动态表达。
*   **ReadGate（状态条件读取）**：利用注意力机制，根据当前的生物状态、环境和记忆，从动态基因组向量中选择性地读取相关信息。
*   **四通道生物记忆**：模拟生物体整合信息的时间尺度，包括稳态（慢速）、发育（时间门控）、偶发（突变/冲击）和群体（物种基准）四个通道。
*   **多元输出头**：使用 Cholesky 参数化预测完整的性状协方差矩阵，以捕捉多效性（Pleiotropy）。

#### 3. 实验设计与对比
研究在涵盖生命四大界的四个数据集上进行了评估，所有实验均使用**完全相同的架构和超参数**：
*   **数据集**：
    *   **细菌 (*E. coli*)**：136 个测试株，214 个生长性状。
    *   **真菌 (*S. cerevisiae*)**：195 个测试株，35 个适应性性状。
    *   **动物 (*D. melanogaster*)**：41 个测试株（极小样本），199 个表型。
    *   **植物 (*O. sativa*)**：83 个测试株，36 个农艺性状。
*   **Benchmark（基准方法）**：岭回归 (GBLUP)、随机森林 (Random Forest)、BayesB (ElasticNet)、Lasso。
*   **评估指标**：Pearson 相关系数 $r$、RMSE、MAE、负对数似然 (NLL)、校准误差 (ECE) 及协方差恢复率。

#### 4. 资源与算力
*   **硬件**：使用了 **4 × NVIDIA H100 (80GB)** GPU。
*   **训练时长**：
    *   细菌：12 小时。
    *   酵母：2 天。
    *   果蝇：3 小时（早期停止）。
    *   水稻：4 天。
*   **框架**：基于 JAX 和 Haiku 构建。

#### 5. 实验数量与充分性
*   **实验规模**：涵盖了从原核生物到真核多细胞生物的四大界，性状维度从 35 到 214 不等，样本量从几十到几百不等。
*   **消融实验**：进行了 5 组关键消融实验（移除生物过程层、移除 ReadGate、移除协方差预测、移除 Evo 2 嵌入等），明确了各组件对性能的贡献。
*   **客观性**：通过固定超参数和架构，证明了性能提升源于“生物学结构设计”而非针对特定数据的调优，实验设计较为客观公平。

#### 6. 主要结论与发现
*   **性能飞跃**：BioWorldModel 在所有生物中均显著优于基准方法。在细菌上提升 207%，酵母提升 167%，果蝇（小样本）提升 760%，水稻提升 49%（接近饱和）。
*   **结构驱动**：消融实验证明，移除生物过程层会导致性能下降 23%，移除基础模型嵌入下降 25%，证明了模拟生物生成逻辑的重要性。
*   **多效性捕捉**：模型能够成功恢复性状间的协方差结构（水稻中 $r=0.59$），显示其学习到了真实的生物学耦合。

#### 7. 优点与亮点
*   **通用性**：单一架构跨越四大界，展示了极强的泛化能力。
*   **小样本鲁棒性**：在果蝇数据集（N=41）这种传统统计方法失效的场景下，依然能通过生物结构约束获得有效预测。
*   **生物学可解释性**：将深度学习组件与生物学中心法则（调控、表达等）对应，使模型不再是纯粹的黑盒。

#### 8. 不足与局限
*   **校准不一致**：模型在不同物种上的概率校准表现不一，酵母表现出过度自信，而细菌则校准不足。
*   **动态数据缺失**：虽然架构支持时间序列，但目前测试的数据集多为静态快照，尚未充分验证其在长期发育轨迹上的预测能力。
*   **跨群体验证尚在进行**：目前主要报告了物种内的预测性能，零样本跨群体（如不同地理来源的品种）的迁移能力仍需进一步验证。

（完）
