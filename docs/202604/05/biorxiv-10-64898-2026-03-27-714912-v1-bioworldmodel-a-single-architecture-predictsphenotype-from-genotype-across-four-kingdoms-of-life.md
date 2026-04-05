---
title: "BioWorldModel: a single architecture predictsphenotype from genotype across four kingdoms of life"
title_zh: BioWorldModel：一种跨越生命四大界从基因型预测表型的单一架构
authors: "Shaik, K. H. B., Sahu, A."
date: 2026-03-31
pdf: "https://www.biorxiv.org/content/10.64898/2026.03.27.714912v1.full.pdf"
tags: ["query:med-ai"]
score: 9.0
evidence: 基因型到表型预测的世界模型架构
tldr: BioWorldModel 是一种跨物种的表型预测架构，涵盖细菌、真菌、动物和植物四大界。该模型摒弃了传统的静态关联方法，通过模拟生物学过程（调控、表达、通路、细胞）将基因型转化为表型。它利用冻结的基因嵌入和状态调节注意力机制，在多种生物的数百种性状预测中显著优于传统模型，证明了模拟生物生成过程在捕捉复杂性状方面的优越性。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-27-714912-v1/fig-001.webp\", \"caption\": \"Figure 2: Comprehensive evaluation across all four kingdoms. (Row A) Point prediction accuracy: BioWorldModel outperforms Ridge (GBLUP) and Random Forest baselines in all organisms. E. coli : mean r = 0.678 (+207% vs ridge); S. cerevisiae: r = 0.915 (+167%); D. melanogaster : r = 0.499 (+760%); O. sativa: r = 0.995 (+49%). (Row B) Calibration quality: Expected calibration error (ECE) varies across organisms. Rice shows excellent calibration (ECE = 0.054), Drosophila moderate (ECE = 0.192), while bacteria and yeast require improvement (ECE > 0.47). Prediction interval coverage plotted against target coverage with perfect calibration shown as diagonal. (Row C) Uncertainty decomposition: Epistemic (model) vs aleatoric (irreducible) uncertainty. Epistemic-error correlation indicates model’s awareness of its limitations: rice r = 0.652, Drosophila r = 0.110, E. coli r = 0.078, yeast r = 0.060. Epistemic/aleatoric ratio shows relative contribution of model uncertainty.\", \"page\": 7, \"index\": 1, \"width\": 904, \"height\": 799}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-27-714912-v1/fig-002.webp\", \"caption\": \"Figure 4: Uncertainty decomposition across all four organisms. (Row A) Epistemic (model) vs aleatoric (irreducible) uncertainty in stacked bars for each organism. Epistemic/aleatoric ratio varies: yeast shows highest ratio (0.777, model-dominated), E. coli lowest (0.235, noisedominated), rice and Drosophila intermediate (0.604 and 0.142 respectively). (Row B) Epistemic uncertainty correlates with prediction error in all organisms, demonstrating model awareness of its limitations. Strongest correlation in rice (r = 0.652), moderate in Drosophila (r = 0.110), weaker in E. coli (r = 0.078) and yeast (r = 0.060). Scatter plots show simulated data with fitted regression lines. High epistemic uncertainty reliably indicates regions where predictions are less trustworthy.\", \"page\": 10, \"index\": 2, \"width\": 905, \"height\": 602}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-27-714912-v1/fig-003.webp\", \"caption\": \"Figure 3: Cross-kingdom performance and generalization. (A) Sample size effects: Performance vs test sample count. Small-sample strength demonstrated in Drosophila (N=41, r=0.499). Saturation approaches in rice (N=83, r=0.995). (B) Trait dimensionality: Performance vs number of traits. High-dimensional regime (E. coli : 214 traits, D. melanogaster : 199 traits) shows biological structure stabilizes learning. (C) Covariance structure recovery: Correlation between predicted and empirical trait covariances. Rice shows strongest recovery (r=0.594), E. coli moderate (r=0.387), suggesting learned pleiotropy structure captures real biology.\", \"page\": 8, \"index\": 3, \"width\": 903, \"height\": 716}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-27-714912-v1/fig-004.webp\", \"caption\": \"Table 3: Extended Data Table 1: Ablation study on E. coli confirms each component contributes.\", \"page\": 19, \"index\": 4, \"width\": 818, \"height\": 361}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-27-714912-v1/fig-005.webp\", \"caption\": \"Table 2: Probabilistic quality varies across organisms.\", \"page\": 9, \"index\": 5, \"width\": 940, \"height\": 226}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-27-714912-v1/fig-006.webp\", \"caption\": \"Table 4: Extended Data Table 2: Comprehensive baseline comparison across all four organisms. We evaluated five classical methods on the same train/test splits. Ridge regression (GBLUP) and Random Forest are shown in main text as representative baselines; BayesB (ElasticNet proxy) and Lasso provide additional benchmarks. All baselines trained per-trait with hyperparameter tuning. BioWorldModel trained once per organism with fixed architecture, predicting all traits jointly.\", \"page\": 20, \"index\": 6, \"width\": 960, \"height\": 860}]"
motivation: 传统模型将基因型编码为静态输入并独立处理性状，忽略了生物体在不同环境下解释基因组的动态过程。
method: 构建了一个包含调控、表达、通路和细胞四个生物过程层的架构，通过状态调节注意力机制动态预测多元性状分布。
result: "在细菌、酵母、果蝇和水稻的数百个表型预测中，该模型表现远超岭回归等传统方法，相关性提升最高达 760%。"
conclusion: 模拟生物学产生表型的动态过程而非简单的基因型-表型关联，是提升预测准确性的关键驱动力。
---

## 摘要
相同的基因组在不同条件下会产生不同的表型，然而现有的预测模型通常仅对基因型进行一次编码，并将每个性状视为相互独立。在本文中，我们展示了将表型生成过程表示为一个动态生物学过程，可以彻底改变细菌、真菌、动物和植物的预测准确性。BioWorldModel 学习生物体如何解读其基因组：受个体变异调制的冻结基因嵌入（物种上下文）通过四个响应环境和时间的生物过程层（调控 [->] 表达 [->] 通路 [->] 细胞）。一种状态条件注意力机制重新读取这种动态表示，从而预测完整的多元性状分布。在无需修改的情况下，该架构在 214 个细菌生长性状上实现了平均相关系数 r = 0.678（比岭回归提升 207%），在 35 个酵母适应度性状上实现了 r = 0.915（提升 167%），在小样本情况下的 199 个果蝇表型上实现了 r = 0.499（提升 760%），在 36 个水稻性状上实现了 r = 0.995（提升 49%）。消融实验证实，驱动性能提升的是对生物过程的建模，而非模型规模。当神经架构能够表征生物学如何生成表型，而不仅仅是将基因型与结果相关联时，它们就能捕捉到静态方法所遗漏的信息。

## Abstract
The same genome produces different phenotypes in different conditions--yet predictive models encode genotype once and treat each trait independently. Here we show that representing phenotype generation as a dynamic biological process transforms predictive accuracy across bacteria, fungi, animals and plants.

BioWorldModel learns how organisms interpret their genome: frozen gene embeddings (species context) modulated by individual variation pass through four biological process layers (regulation [-&gt;] expression [-&gt;] pathway [-&gt;] cellular) that respond to environment and time. A state-conditioned attention mechanism rereads this dynamic representation, predicting full multivariate trait distributions.

Without modification, the architecture achieves mean correlation r = 0.678 on 214 bacterial growth traits (207% better than ridge regression), r = 0.915 on 35 yeast fitness traits (167% better), r = 0.499 on 199 fly phenotypes in small-sample regime (760% better), and r = 0.995 on 36 rice traits (49% better). Ablations confirm that modeling biological process--not model size--drives performance. When neural architectures represent how biology generates phenotype rather than merely associating genotype with outcome, they capture what static methods miss.

---

## 论文详细总结（自动生成）

### BioWorldModel 论文深度总结

#### 1. 核心问题与研究动机
*   **核心问题**：传统的基因组预测模型（如岭回归、随机森林）通常将基因型视为静态输入，并独立预测每个性状。然而，生物学本质是动态的——相同的基因组在不同环境、时间和生理状态下会产生截然不同的表型。
*   **研究动机**：作者认为基因组不是被简单“解码”的，而是被“解读”的。预测准确性的瓶颈在于模型缺乏对生物生成过程（从基因调控到细胞反应）的模拟。因此，需要一种能够捕捉环境调制和多效性（Pleiotropy）的统一架构。

#### 2. 方法论：BioWorldModel 架构
BioWorldModel 的核心思想是将表型生成建模为受环境约束的动态生物过程，包含四大创新：
*   **因子化基因表示**：
    *   **物种上下文**：使用冻结的 **Evo 2 (7B)** 基础模型嵌入（4096维），捕捉进化的功能约束。
    *   **个体变异**：通过 6 个 SNP 特征（杂合/纯合计数、剂量等）学习个体对参考基因组的扰动。
*   **生物过程栈 (BioProcessStack)**：构建了四个显式层：**调控 → 表达 → 通路 → 细胞**。每一层都通过环境和时间信号进行门控调制，模拟基因在不同条件下的差异化表达。
*   **状态条件读取 (ReadGate)**：采用注意力机制，根据生物体当前的状态、环境和记忆，动态地从基因组表示中“读取”相关的遗传信息。
*   **四通道生物记忆**：
    *   **稳态记忆**：跟踪异体调节基准。
    *   **发育记忆**：捕捉关键的发育窗口（如开花、变态）。
    *   **情节记忆**：存储生物冲击（如感染、受伤）。
    *   **群体记忆**：学习物种基准的偏差。
*   **多元输出头**：使用 Cholesky 参数化预测全性状协方差矩阵，从而建模基因多效性。

#### 3. 实验设计
*   **数据集与场景**：涵盖生命四大界，性状维度从 35 到 214 不等：
    *   **细菌 (*E. coli*)**：214 个生长适应度性状。
    *   **真菌 (*S. cerevisiae*)**：35 个菌落大小性状。
    *   **动物 (*D. melanogaster*)**：199 个形态、行为和生活史性状（极小样本场景）。
    *   **植物 (*O. sativa*)**：36 个农艺性状。
*   **Benchmark 与对比方法**：
    *   **基准方法**：岭回归 (GBLUP)、随机森林 (Random Forest)、BayesB (ElasticNet)、Lasso。
    *   **评估指标**：Pearson 相关系数 (r)、均方根误差 (RMSE)、负对数似然 (NLL)、校准误差 (ECE)。

#### 4. 资源与算力
*   **硬件**：使用了 **4 × NVIDIA H100 (80GB)** GPU。
*   **软件框架**：基于 JAX 和 Haiku。
*   **训练时长**：
    *   细菌：12 小时。
    *   酵母：2 天。
    *   果蝇：3 小时（早停）。
    *   水稻：4 天。
*   **参数量**：完整系统包含约 **2910 万**个参数。

#### 5. 实验数量与充分性
*   **实验规模**：在四个完全不同的物种上进行了验证，涉及数百个性状和数万个遗传标记。
*   **消融实验**：在 *E. coli* 数据集上进行了 5 组消融实验，分别验证了生物过程栈、ReadGate、协方差建模、基础模型嵌入等组件的贡献。
*   **公平性**：所有基准方法均经过了充分的超参数调优（5 折交叉验证），而 BioWorldModel 在所有物种中使用了**完全相同**的架构和超参数，证明了其泛化能力而非过拟合。

#### 6. 主要结论与发现
*   **性能飞跃**：BioWorldModel 在所有指标上均大幅领先。在果蝇的小样本场景下，相关性提升了 **760%**；在水稻上达到了近乎完美的预测（r = 0.995）。
*   **结构胜过规模**：消融实验显示，移除生物过程层会导致性能下降 23%，移除基础模型嵌入下降 25%。这证明性能提升源于对生物逻辑的模拟，而非单纯增加参数。
*   **多效性捕捉**：模型成功恢复了真实的性状协方差结构（水稻中 r = 0.59），证明其能学习到基因如何同时影响多个性状。

#### 7. 优点与亮点
*   **跨界统一性**：单一架构无需修改即可处理从原核生物到高等真核生物的预测任务。
*   **生物学可解释性**：通过显式的调控、表达等层级建模，使神经网络的内部逻辑与生物学中心法则相呼应。
*   **小样本鲁棒性**：在样本量极少（N=41）的情况下依然表现强劲，这对稀有疾病或孤儿作物研究具有重要意义。

#### 8. 不足与局限
*   **校准不一致**：模型在不同物种上的概率校准表现不一，酵母表现出过度自信，而细菌则校准不足。
*   **时间动态未充分验证**：虽然架构支持时间序列，但当前实验主要基于静态快照数据，尚未在真正的纵向发育数据上验证记忆通道。
*   **零样本迁移待证**：目前主要报告了物种内的预测性能，跨种群、跨地理区域的零样本迁移能力仍处于实验阶段。

（完）
