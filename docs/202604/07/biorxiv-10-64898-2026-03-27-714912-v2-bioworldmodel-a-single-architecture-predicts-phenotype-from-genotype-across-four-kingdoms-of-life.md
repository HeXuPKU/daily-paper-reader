---
title: "BioWorldModel: a single architecture predicts phenotype from genotype across four kingdoms of life"
title_zh: BioWorldModel：一种跨越四个生物界的从基因型预测表型的单一架构
authors: "Shaik, K. H. B., Sahu, A."
date: 2026-04-01
pdf: "https://www.biorxiv.org/content/10.64898/2026.03.27.714912v2.full.pdf"
tags: ["query:med-ai"]
score: 9.0
evidence: 用于从基因型预测表型的世界模型架构
tldr: BioWorldModel 是一种统一的神经网络架构，通过模拟生物过程（调控、表达、通路、细胞）将基因型映射为表型。它不仅考虑个体变异，还整合了环境和时间因素，在细菌、真菌、动物和植物四大界生物的多种性状预测中表现卓越，显著优于传统静态关联方法，证明了模拟生物生成过程对提高预测准确性的关键作用。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-27-714912-v2/fig-001.webp\", \"caption\": \"Figure 2: Comprehensive evaluation across all four kingdoms. (Row A) Point prediction accuracy: BioWorldModel outperforms Ridge (GBLUP) and Random Forest baselines in all organisms. E. coli : mean r = 0.678 (+207% vs ridge); S. cerevisiae: r = 0.915 (+167%); D. melanogaster : r = 0.499 (+760%); O. sativa: r = 0.995 (+49%). (Row B) Calibration quality: Expected calibration error (ECE) varies across organisms. Rice shows excellent calibration (ECE = 0.054), Drosophila moderate (ECE = 0.192), while bacteria and yeast require improvement (ECE > 0.47). Prediction interval coverage plotted against target coverage with perfect calibration shown as diagonal. (Row C) Uncertainty decomposition: Epistemic (model) vs aleatoric (irreducible) uncertainty. Epistemic-error correlation indicates model’s awareness of its limitations: rice r = 0.652, Drosophila r = 0.110, E. coli r = 0.078, yeast r = 0.060. Epistemic/aleatoric ratio shows relative contribution of model uncertainty.\", \"page\": 7, \"index\": 1, \"width\": 904, \"height\": 799}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-27-714912-v2/fig-002.webp\", \"caption\": \"Figure 4: Uncertainty decomposition across all four organisms. (Row A) Epistemic (model) vs aleatoric (irreducible) uncertainty in stacked bars for each organism. Epistemic/aleatoric ratio varies: yeast shows highest ratio (0.777, model-dominated), E. coli lowest (0.235, noisedominated), rice and Drosophila intermediate (0.604 and 0.142 respectively). (Row B) Epistemic uncertainty correlates with prediction error in all organisms, demonstrating model awareness of its limitations. Strongest correlation in rice (r = 0.652), moderate in Drosophila (r = 0.110), weaker in E. coli (r = 0.078) and yeast (r = 0.060). Scatter plots show simulated data with fitted regression lines. High epistemic uncertainty reliably indicates regions where predictions are less trustworthy.\", \"page\": 10, \"index\": 2, \"width\": 905, \"height\": 602}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-27-714912-v2/fig-003.webp\", \"caption\": \"Figure 3: Cross-kingdom performance and generalization. (A) Sample size effects: Performance vs test sample count. Small-sample strength demonstrated in Drosophila (N=41, r=0.499). Saturation approaches in rice (N=83, r=0.995). (B) Trait dimensionality: Performance vs number of traits. High-dimensional regime (E. coli : 214 traits, D. melanogaster : 199 traits) shows biological structure stabilizes learning. (C) Covariance structure recovery: Correlation between predicted and empirical trait covariances. Rice shows strongest recovery (r=0.594), E. coli moderate (r=0.387), suggesting learned pleiotropy structure captures real biology.\", \"page\": 8, \"index\": 3, \"width\": 903, \"height\": 716}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-27-714912-v2/fig-004.webp\", \"caption\": \"Table 3: Extended Data Table 1: Ablation study on E. coli confirms each component contributes.\", \"page\": 19, \"index\": 4, \"width\": 818, \"height\": 361}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-27-714912-v2/fig-005.webp\", \"caption\": \"Table 2: Probabilistic quality varies across organisms.\", \"page\": 9, \"index\": 5, \"width\": 940, \"height\": 226}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-27-714912-v2/fig-006.webp\", \"caption\": \"Table 4: Extended Data Table 2: Comprehensive baseline comparison across all four organisms. We evaluated five classical methods on the same train/test splits. Ridge regression (GBLUP) and Random Forest are shown in main text as representative baselines; BayesB (ElasticNet proxy) and Lasso provide additional benchmarks. All baselines trained per-trait with hyperparameter tuning. BioWorldModel trained once per organism with fixed architecture, predicting all traits jointly.\", \"page\": 20, \"index\": 6, \"width\": 960, \"height\": 860}]"
motivation: 传统模型将基因型编码为静态且独立的性状，忽略了生物体在不同环境下动态解释基因组的过程。
method: 提出一种包含四个生物过程层（调控、表达、通路、细胞）的架构，利用状态调节注意力机制结合环境和时间预测多元性状分布。
result: "在细菌、酵母、果蝇和水稻的数百个性状预测中，该模型比传统岭回归等方法提升了 49% 到 760% 不等的准确率。"
conclusion: 模拟生物生成表型的动态过程而非简单的基因关联，是提升基因型到表型预测能力的核心驱动力。
---

## 摘要
相同的基因组在不同条件下会产生不同的表型，然而现有的预测模型通常仅对基因型进行一次编码，并将每个性状视为相互独立。在本文中，我们展示了将表型生成表示为一个动态生物过程，能够显著提升细菌、真菌、动物和植物的预测准确性。BioWorldModel 学习生物体如何解读其基因组：由个体变异调制的冻结基因嵌入（物种背景）通过四个响应环境和时间的生物过程层（调控 [->] 表达 [->] 通路 [->] 细胞）。一种状态条件注意力机制重新读取这种动态表示，从而预测完整的多元性状分布。在无需修改的情况下，该架构在 214 个细菌生长性状上实现了平均相关系数 r = 0.678（比岭回归提高 207%），在 35 个酵母适应性性状上实现了 r = 0.915（提高 167%），在小样本情况下的 199 个果蝇表型上实现了 r = 0.499（提高 760%），在 36 个水稻性状上实现了 r = 0.995（提高 49%）。消融实验证实，驱动性能提升的是对生物过程的建模，而非模型规模。当神经架构能够表征生物学如何生成表型，而不仅仅是将基因型与结果相关联时，它们就能捕捉到静态方法所遗漏的信息。

## Abstract
The same genome produces different phenotypes in different conditions--yet predictive models encode genotype once and treat each trait independently. Here we show that representing phenotype generation as a dynamic biological process transforms predictive accuracy across bacteria, fungi, animals and plants.

BioWorldModel learns how organisms interpret their genome: frozen gene embeddings (species context) modulated by individual variation pass through four biological process layers (regulation [-&gt;] expression [-&gt;] pathway [-&gt;] cellular) that respond to environment and time. A state-conditioned attention mechanism rereads this dynamic representation, predicting full multivariate trait distributions.

Without modification, the architecture achieves mean correlation r = 0.678 on 214 bacterial growth traits (207% better than ridge regression), r = 0.915 on 35 yeast fitness traits (167% better), r = 0.499 on 199 fly phenotypes in small-sample regime (760% better), and r = 0.995 on 36 rice traits (49% better). Ablations confirm that modeling biological process--not model size--drives performance. When neural architectures represent how biology generates phenotype rather than merely associating genotype with outcome, they capture what static methods miss.

---

## 论文详细总结（自动生成）

这是一份关于论文《BioWorldModel: a single architecture predicts phenotype from genotype across four kingdoms of life》的结构化深入总结：

### 1. 核心问题与研究背景
传统的基因组预测方法（如岭回归、随机森林）通常将基因型视为静态特征，并对每个性状进行独立训练。然而，生物学本质是动态的：相同的基因组在不同的环境、时间和生理状态下会被“解释”出不同的表型。
**研究动机：** 论文旨在探索如果神经网络架构能够模拟生物体生成表型的过程（即动态解释基因组，而非简单的统计关联），是否能显著提高跨物种、跨性状的预测准确性。

### 2. 方法论：BioWorldModel 架构
该模型通过四个核心创新点将生物学原理实例化：
*   **因子化基因表示：** 将基因表示分为两部分：一是来自预训练大模型 **Evo 2 (7B)** 的冻结嵌入（代表物种水平的进化背景），二是由个体 SNP 特征学习到的调制信号（代表个体变异）。
*   **BioProcessStack（生物过程栈）：** 包含四个层（调控 → 表达 → 通路 → 细胞），每一层都通过环境和时间信号进行门控调制。这模拟了基因组如何根据外部条件动态产生分子状态。
*   **ReadGate（状态条件读取）：** 采用注意力机制，根据生物体当前的状态、环境和记忆，从动态基因组向量中选择性地读取相关信息。
*   **四通道生物记忆：** 模拟生物体在不同时间尺度上整合信息的能力，包括稳态（慢速）、发育（时间门控）、偶发（冲击事件）和群体（物种基准）记忆。
*   **多元输出：** 使用 Cholesky 参数化预测完整的性状协方差矩阵，以捕捉多效性（一个基因影响多个性状）。

### 3. 实验设计
*   **数据集：** 涵盖四大生物界：
    *   **细菌 (*E. coli*)：** 214 个生长性状，3,221 个标记。
    *   **真菌 (*S. cerevisiae*)：** 35 个适应性性状，83,343 个 SNP。
    *   **动物 (*D. melanogaster*)：** 199 个表型（形态、行为等），34,006 个 SNP。
    *   **植物 (*O. sativa*)：** 36 个农艺性状，35,404 个 SNP。
*   **基准模型 (Benchmarks)：** 岭回归 (GBLUP)、随机森林 (Random Forest)、BayesB (ElasticNet)、Lasso。
*   **评估指标：** Pearson 相关系数 (r)、均方根误差 (RMSE)、负对数似然 (NLL)、预期校准误差 (ECE) 等。

### 4. 资源与算力
*   **硬件：** 使用了 **4 × NVIDIA H100 (80GB)** GPU。
*   **软件框架：** JAX 0.6.2 和 Haiku 0.0.10。
*   **训练时长：** 
    *   大肠杆菌：12 小时。
    *   酵母：2 天。
    *   果蝇：3 小时（早停）。
    *   水稻：4 天。
*   **推理速度：** 每个个体每步约 1-3 秒（CPU）。

### 5. 实验数量与充分性
*   **实验规模：** 论文在四个完全不同的生物界上进行了验证，涉及数百个性状和数千个样本，实验覆盖面极广。
*   **消融实验：** 进行了 5 组关键消融实验（移除生物过程栈、移除 ReadGate、移除 Evo 2 嵌入等），明确了各组件对性能的贡献。
*   **客观性：** 所有物种使用完全相同的架构和超参数，未针对特定物种调优，证明了架构的通用性和鲁棒性。

### 6. 主要结论与发现
*   **性能飞跃：** BioWorldModel 在所有物种上均大幅领先。在细菌上提升 207%，酵母提升 167%，果蝇（小样本）提升 760%，水稻提升 49%。
*   **结构胜过规模：** 消融实验证明，性能提升主要源于对生物过程的建模（如环境调制和条件读取），而非单纯增加参数量。
*   **捕捉多效性：** 模型能够恢复真实的性状协方差结构，尤其在水稻和大肠杆菌中表现显著。
*   **不确定性感知：** 模型能够区分认知不确定性（模型知识不足）和偶然不确定性（数据噪声）。

### 7. 优点与亮点
*   **跨界通用性：** 单一架构无需修改即可应用于从原核生物到高等真核生物。
*   **小样本鲁棒性：** 在果蝇数据集（N=41）中，传统方法失效，而该模型凭借生物学结构约束仍能获得有效预测。
*   **整合基础模型：** 成功将基因组基础模型 (Evo 2) 的进化知识转化为表型预测能力。
*   **可解释性：** 架构设计符合生物学中心法则和调控逻辑，比纯黑盒模型更具生物学意义。

### 8. 不足与局限
*   **校准不均匀：** 虽然在水稻上校准良好，但在酵母和细菌上存在过度自信或信心不足的问题，概率预测的成熟度有待提高。
*   **时间动态未充分验证：** 尽管架构支持递归处理，但当前测试的数据集多为静态快照，尚未在真正的纵向时间序列数据上完全验证其记忆通道。
*   **零样本迁移待证：** 跨群体（如从亚洲水稻迁移到非洲水稻）的零样本预测实验仍在进行中，尚未在本文中完全展示。

（完）
