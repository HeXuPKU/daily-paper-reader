---
title: "BioWorldModel: a single architecture predictsphenotype from genotype across four kingdoms of life"
title_zh: BioWorldModel：一种跨越生命四大界从基因型预测表型的单一架构
authors: "Shaik, K. H. B., Sahu, A."
date: 2026-03-31
pdf: "https://www.biorxiv.org/content/10.64898/2026.03.27.714912v1.full.pdf"
tags: ["query:med-ai"]
score: 10.0
evidence: 从基因型和环境预测表型的世界模型架构
tldr: BioWorldModel是一个跨物种的表型预测架构，涵盖细菌、真菌、动物和植物。它打破了传统模型将基因型与性状简单关联的局限，通过模拟从基因调节到细胞活动的四个生物过程层，结合环境和时间因素，实现了对多变量性状分布的高精度预测。该研究证明，模拟生物生成表型的动态过程比单纯增加模型规模更能提升预测性能。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-27-714912-v1/fig-001.webp\", \"caption\": \"Figure 2: Comprehensive evaluation across all four kingdoms. (Row A) Point prediction accuracy: BioWorldModel outperforms Ridge (GBLUP) and Random Forest baselines in all organisms. E. coli : mean r = 0.678 (+207% vs ridge); S. cerevisiae: r = 0.915 (+167%); D. melanogaster : r = 0.499 (+760%); O. sativa: r = 0.995 (+49%). (Row B) Calibration quality: Expected calibration error (ECE) varies across organisms. Rice shows excellent calibration (ECE = 0.054), Drosophila moderate (ECE = 0.192), while bacteria and yeast require improvement (ECE > 0.47). Prediction interval coverage plotted against target coverage with perfect calibration shown as diagonal. (Row C) Uncertainty decomposition: Epistemic (model) vs aleatoric (irreducible) uncertainty. Epistemic-error correlation indicates model’s awareness of its limitations: rice r = 0.652, Drosophila r = 0.110, E. coli r = 0.078, yeast r = 0.060. Epistemic/aleatoric ratio shows relative contribution of model uncertainty.\", \"page\": 7, \"index\": 1, \"width\": 904, \"height\": 799}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-27-714912-v1/fig-002.webp\", \"caption\": \"Figure 4: Uncertainty decomposition across all four organisms. (Row A) Epistemic (model) vs aleatoric (irreducible) uncertainty in stacked bars for each organism. Epistemic/aleatoric ratio varies: yeast shows highest ratio (0.777, model-dominated), E. coli lowest (0.235, noisedominated), rice and Drosophila intermediate (0.604 and 0.142 respectively). (Row B) Epistemic uncertainty correlates with prediction error in all organisms, demonstrating model awareness of its limitations. Strongest correlation in rice (r = 0.652), moderate in Drosophila (r = 0.110), weaker in E. coli (r = 0.078) and yeast (r = 0.060). Scatter plots show simulated data with fitted regression lines. High epistemic uncertainty reliably indicates regions where predictions are less trustworthy.\", \"page\": 10, \"index\": 2, \"width\": 905, \"height\": 602}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-27-714912-v1/fig-003.webp\", \"caption\": \"Figure 3: Cross-kingdom performance and generalization. (A) Sample size effects: Performance vs test sample count. Small-sample strength demonstrated in Drosophila (N=41, r=0.499). Saturation approaches in rice (N=83, r=0.995). (B) Trait dimensionality: Performance vs number of traits. High-dimensional regime (E. coli : 214 traits, D. melanogaster : 199 traits) shows biological structure stabilizes learning. (C) Covariance structure recovery: Correlation between predicted and empirical trait covariances. Rice shows strongest recovery (r=0.594), E. coli moderate (r=0.387), suggesting learned pleiotropy structure captures real biology.\", \"page\": 8, \"index\": 3, \"width\": 903, \"height\": 716}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-27-714912-v1/fig-004.webp\", \"caption\": \"Table 3: Extended Data Table 1: Ablation study on E. coli confirms each component contributes.\", \"page\": 19, \"index\": 4, \"width\": 818, \"height\": 361}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-27-714912-v1/fig-005.webp\", \"caption\": \"Table 2: Probabilistic quality varies across organisms.\", \"page\": 9, \"index\": 5, \"width\": 940, \"height\": 226}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-27-714912-v1/fig-006.webp\", \"caption\": \"Table 4: Extended Data Table 2: Comprehensive baseline comparison across all four organisms. We evaluated five classical methods on the same train/test splits. Ridge regression (GBLUP) and Random Forest are shown in main text as representative baselines; BayesB (ElasticNet proxy) and Lasso provide additional benchmarks. All baselines trained per-trait with hyperparameter tuning. BioWorldModel trained once per organism with fixed architecture, predicting all traits jointly.\", \"page\": 20, \"index\": 6, \"width\": 960, \"height\": 860}]"
motivation: 传统预测模型通常将基因型与性状独立关联，忽略了基因组在不同环境和时间下产生表型的动态生物学过程。
method: 提出BioWorldModel架构，利用冻结的基因嵌入和个体变异，通过模拟调节、表达、通路和细胞四个生物过程层，并结合状态调节注意力机制进行预测。
result: "在细菌、酵母、果蝇和水稻的数百种性状预测中，该模型表现显著优于传统回归方法，相关性提升最高达760%。"
conclusion: 将神经网络架构设计为模拟生物学产生表型的过程，而非简单的关联映射，是捕获复杂生物学特征的关键。
---

## 摘要
相同的基因组在不同条件下会产生不同的表型，然而现有的预测模型通常仅对基因型进行一次编码，并将每个性状视为相互独立。在本文中，我们展示了将表型生成过程表示为一个动态生物学过程，可以彻底改变对细菌、真菌、动物和植物的预测准确性。BioWorldModel 学习生物体如何解读其基因组：由个体变异调制的冻结基因嵌入（物种上下文）通过四个生物过程层（从调控到表达，再到通路，最后到细胞层级），这些层级能够对环境和时间做出响应。一种状态条件注意力机制通过重新读取这种动态表示，来预测完整的多元性状分布。在无需任何修改的情况下，该架构在 214 种细菌生长性状上实现了平均相关系数 r = 0.678（比岭回归提升 207%），在 35 种酵母适应性性状上达到 r = 0.915（提升 167%），在小样本情况下的 199 种果蝇表型上达到 r = 0.499（提升 760%），在 36 种水稻性状上达到 r = 0.995（提升 49%）。消融实验证实，驱动性能提升的核心在于对生物过程的建模，而非模型规模。当神经架构能够表征生物学生成表型的内在机制，而不仅仅是将基因型与结果进行关联时，它们就能捕捉到静态方法所遗漏的关键信息。

## Abstract
The same genome produces different phenotypes in different conditions--yet predictive models encode genotype once and treat each trait independently. Here we show that representing phenotype generation as a dynamic biological process transforms predictive accuracy across bacteria, fungi, animals and plants. BioWorldModel learns how organisms interpret their genome: frozen gene embeddings (species context) modulated by individual variation pass through four biological process layers (regulation to expression to pathway to cellular) that respond to environment and time. A state-conditioned attention mechanism rereads this dynamic representation, predicting full multivariate trait distributions. Without modification, the architecture achieves mean correlation r = 0.678 on 214 bacterial growth traits (207% better than ridge regression), r = 0.915 on 35 yeast fitness traits (167% better), r = 0.499 on 199 fly phenotypes in small-sample regime (760% better), and r = 0.995 on 36 rice traits (49% better). Ablations confirm that modeling biological process--not model size--drives performance. When neural architectures represent how biology generates phenotype rather than merely associating genotype with outcome, they capture what static methods miss.

---

## 论文详细总结（自动生成）

### BioWorldModel 论文深度总结

#### 1. 核心问题与整体含义（研究动机和背景）
传统的基因组预测模型（如岭回归、随机森林）通常将基因型视为静态编码，并假设基因型与表型之间是简单的统计关联。然而，生物学本质是动态的：相同的基因组在不同环境、时间和生理状态下会产生截然不同的表型。论文指出，基因不是被简单“解码”的，而是被“解读”的。现有的方法忽略了这种上下文相关的生物过程，导致在处理多效性（一个基因影响多个性状）和环境互作时表现不佳。BioWorldModel 的核心动机是构建一个能够模拟生物体如何根据环境动态解读基因组的“世界模型”，从而实现跨物种、高精度的表型预测。

#### 2. 方法论：核心思想与关键技术
BioWorldModel 采用单一架构，通过四个关键创新模拟生物生成表型的过程：
*   **混合基因表示**：将基因表示分解为物种级的“进化上下文”（使用预训练的 Evo 2 7B 模型生成的冻结嵌入）和个体级的“变异调制”（基于 SNP 特征学习到的扰动）。
*   **生物过程栈 (BioProcessStack)**：设计了四个功能层（调控 $\to$ 表达 $\to$ 通路 $\to$ 细胞），每一层都通过环境和时间信号进行门控调制，模拟基因组在不同条件下的动态表达。
*   **状态条件读取门 (ReadGate)**：利用注意力机制，根据生物体当前的状态、环境和记忆，从基因组表示中选择性地读取相关信息。
*   **四通道生物记忆**：引入并行记忆机制，分别捕捉稳态（长期）、发育（关键窗口）、偶发（突发冲击）和群体（物种基准）四个时间尺度的信息。
*   **多元输出头**：使用 Cholesky 参数化预测完整的性状协方差矩阵，从而显式建模基因多效性。

#### 3. 实验设计
研究在生命四大界的四个代表性数据集上进行了评估，所有实验均使用相同的架构和超参数：
*   **数据集**：
    *   **细菌 (*E. coli*)**：678 个菌株，214 种生长适应性性状。
    *   **真菌 (*S. cerevisiae*)**：971 个分离株，35 种适应性性状。
    *   **动物 (*D. melanogaster*)**：205 个果蝇系，199 种形态、行为和生活史性状（小样本挑战）。
    *   **植物 (*O. sativa*)**：413 个水稻品种，36 种农艺性状。
*   **基准模型 (Benchmarks)**：岭回归 (GBLUP)、随机森林 (Random Forest)、BayesB (ElasticNet)、Lasso 以及均值基准。
*   **评估指标**：Pearson 相关系数 ($r$)、均方根误差 (RMSE)、负对数似然 (NLL) 和校准误差 (ECE)。

#### 4. 资源与算力
*   **硬件**：使用了 4 张 NVIDIA H100 GPU (80GB)。
*   **软件框架**：基于 JAX 和 Haiku 开发。
*   **训练时长**：
    *   大肠杆菌：约 12 小时。
    *   酵母：约 2 天。
    *   果蝇：约 3 小时（由于样本量小，提前停止）。
    *   水稻：约 4 天。
*   **推理速度**：在 CPU 上每样本每步约 1-3 秒。

#### 5. 实验数量与充分性
论文进行了多维度的实验验证：
*   **跨物种验证**：覆盖了四大界，证明了架构的普适性。
*   **消融实验**：在 *E. coli* 上进行了 5 组消融实验，分别移除生物过程栈、读取门、协方差建模等，证实了生物学结构设计（而非模型规模）是性能提升的主因。
*   **不确定性分析**：通过 MC Dropout 分解了认识不确定性（模型）和偶然不确定性（噪声）。
*   **充分性评价**：实验设计较为客观，使用了标准的训练/测试集划分，并对比了多种主流遗传学预测方法，样本量从几十到近千不等，具有较强的说服力。

#### 6. 主要结论与发现
*   **性能飞跃**：BioWorldModel 在所有物种上的表现均大幅优于传统方法。在果蝇（小样本）上提升达 760%，在细菌上提升 207%，在水稻上接近饱和（$r=0.995$）。
*   **结构胜过规模**：消融实验显示，移除生物过程层会导致性能下降 23%，移除预训练基因嵌入下降 25%。
*   **捕捉多效性**：模型能够成功恢复性状间的协方差结构（如水稻的协方差恢复相关性达 0.59），说明其学到了真实的生物学关联。
*   **小样本鲁棒性**：在样本量极小（N=41）的情况下，生物学先验结构能有效稳定学习过程。

#### 7. 优点
*   **生物学一致性**：架构设计紧扣生物学中心法则和动态调节机制，具有很强的可解释性潜力。
*   **通用性**：单一架构无需针对物种进行超参数微调即可在四大界生效。
*   **多性状联合预测**：通过多元分布预测，解决了传统方法孤立看待性状的问题。
*   **融合前沿技术**：成功将基因组大模型（Evo 2）的进化知识整合进表型预测框架。

#### 8. 不足与局限
*   **校准质量不均**：虽然水稻的预测区间非常准确，但在细菌和酵母上存在过度自信或信心不足的问题（ECE 较高）。
*   **时间动态未充分验证**：虽然设计了递归架构和记忆通道，但测试数据集多为静态快照，缺乏对纵向发育数据的实际验证。
*   **跨群体迁移待证**：目前主要在同一物种的随机划分集上测试，尚未证明在完全不同的地理群体或育种计划间的零样本迁移能力。
*   **计算成本**：相比于简单的线性回归，深度学习模型的训练和推理成本显著更高。

（完）
