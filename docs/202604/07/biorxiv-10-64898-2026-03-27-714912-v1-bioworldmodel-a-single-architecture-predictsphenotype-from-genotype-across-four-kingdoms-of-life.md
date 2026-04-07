---
title: "BioWorldModel: a single architecture predictsphenotype from genotype across four kingdoms of life"
title_zh: BioWorldModel：一种跨越生命四大界的从基因型预测表型的统一架构
authors: "Shaik, K. H. B., Sahu, A."
date: 2026-03-31
pdf: "https://www.biorxiv.org/content/10.64898/2026.03.27.714912v1.full.pdf"
tags: ["query:med-ai"]
score: 9.0
evidence: 使用世界模型架构从基因型预测表型的大规模基因组模型
tldr: BioWorldModel 是一种跨物种的表型预测架构，通过模拟生物学过程（调控、表达、通路、细胞）将基因型映射为表型。它利用冻结的基因嵌入和个体变异，结合环境与时间因素，在细菌、真菌、动物和植物四大界中均实现了显著优于传统方法的预测精度，证明了模拟生物生成过程比单纯的关联分析更有效。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-27-714912-v1/fig-001.webp\", \"caption\": \"Figure 2: Comprehensive evaluation across all four kingdoms. (Row A) Point prediction accuracy: BioWorldModel outperforms Ridge (GBLUP) and Random Forest baselines in all organisms. E. coli : mean r = 0.678 (+207% vs ridge); S. cerevisiae: r = 0.915 (+167%); D. melanogaster : r = 0.499 (+760%); O. sativa: r = 0.995 (+49%). (Row B) Calibration quality: Expected calibration error (ECE) varies across organisms. Rice shows excellent calibration (ECE = 0.054), Drosophila moderate (ECE = 0.192), while bacteria and yeast require improvement (ECE > 0.47). Prediction interval coverage plotted against target coverage with perfect calibration shown as diagonal. (Row C) Uncertainty decomposition: Epistemic (model) vs aleatoric (irreducible) uncertainty. Epistemic-error correlation indicates model’s awareness of its limitations: rice r = 0.652, Drosophila r = 0.110, E. coli r = 0.078, yeast r = 0.060. Epistemic/aleatoric ratio shows relative contribution of model uncertainty.\", \"page\": 7, \"index\": 1, \"width\": 904, \"height\": 799}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-27-714912-v1/fig-002.webp\", \"caption\": \"Figure 4: Uncertainty decomposition across all four organisms. (Row A) Epistemic (model) vs aleatoric (irreducible) uncertainty in stacked bars for each organism. Epistemic/aleatoric ratio varies: yeast shows highest ratio (0.777, model-dominated), E. coli lowest (0.235, noisedominated), rice and Drosophila intermediate (0.604 and 0.142 respectively). (Row B) Epistemic uncertainty correlates with prediction error in all organisms, demonstrating model awareness of its limitations. Strongest correlation in rice (r = 0.652), moderate in Drosophila (r = 0.110), weaker in E. coli (r = 0.078) and yeast (r = 0.060). Scatter plots show simulated data with fitted regression lines. High epistemic uncertainty reliably indicates regions where predictions are less trustworthy.\", \"page\": 10, \"index\": 2, \"width\": 905, \"height\": 602}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-27-714912-v1/fig-003.webp\", \"caption\": \"Figure 3: Cross-kingdom performance and generalization. (A) Sample size effects: Performance vs test sample count. Small-sample strength demonstrated in Drosophila (N=41, r=0.499). Saturation approaches in rice (N=83, r=0.995). (B) Trait dimensionality: Performance vs number of traits. High-dimensional regime (E. coli : 214 traits, D. melanogaster : 199 traits) shows biological structure stabilizes learning. (C) Covariance structure recovery: Correlation between predicted and empirical trait covariances. Rice shows strongest recovery (r=0.594), E. coli moderate (r=0.387), suggesting learned pleiotropy structure captures real biology.\", \"page\": 8, \"index\": 3, \"width\": 903, \"height\": 716}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-27-714912-v1/fig-004.webp\", \"caption\": \"Table 3: Extended Data Table 1: Ablation study on E. coli confirms each component contributes.\", \"page\": 19, \"index\": 4, \"width\": 818, \"height\": 361}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-27-714912-v1/fig-005.webp\", \"caption\": \"Table 2: Probabilistic quality varies across organisms.\", \"page\": 9, \"index\": 5, \"width\": 940, \"height\": 226}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-27-714912-v1/fig-006.webp\", \"caption\": \"Table 4: Extended Data Table 2: Comprehensive baseline comparison across all four organisms. We evaluated five classical methods on the same train/test splits. Ridge regression (GBLUP) and Random Forest are shown in main text as representative baselines; BayesB (ElasticNet proxy) and Lasso provide additional benchmarks. All baselines trained per-trait with hyperparameter tuning. BioWorldModel trained once per organism with fixed architecture, predicting all traits jointly.\", \"page\": 20, \"index\": 6, \"width\": 960, \"height\": 860}]"
motivation: 传统模型通常将基因型视为静态编码并独立处理性状，忽略了生物体在不同环境下解释基因组的动态生物学过程。
method: 该架构通过四个生物过程层（调控、表达、通路、细胞）处理基因变异，并利用状态条件注意力机制结合环境和时间因素预测多元性状分布。
result: "在细菌、酵母、果蝇和水稻的数百种性状预测中，该模型表现均大幅优于岭回归等传统方法，预测相关性提升了 49% 至 760% 不等。"
conclusion: 研究证明，模拟生物学如何生成表型而非仅仅关联基因型与结果，是提升预测模型捕捉复杂生物学规律的关键。
---

## 摘要
相同的基因组在不同条件下会产生不同的表型，然而目前的预测模型通常只对基因型进行一次编码，并将每种性状独立对待。在本文中，我们展示了将表型生成表示为一个动态生物学过程，能够显著提升细菌、真菌、动物和植物的预测准确性。BioWorldModel 学习生物体如何解读其基因组：由个体变异调制的冻结基因嵌入（物种上下文）通过四个响应环境和时间的生物过程层（调控 [->] 表达 [->] 通路 [->] 细胞）。一种状态条件注意力机制重新读取这种动态表示，从而预测完整的多元性状分布。在无需修改的情况下，该架构在 214 种细菌生长性状上实现了平均相关系数 r = 0.678（比岭回归提高 207%），在 35 种酵母适应性性状上实现了 r = 0.915（提高 167%），在小样本情况下的 199 种果蝇表型上实现了 r = 0.499（提高 760%），在 36 种水稻性状上实现了 r = 0.995（提高 49%）。消融实验证实，驱动性能提升的是对生物过程的建模，而非模型规模。当神经网络架构能够表征生物学如何生成表型，而不仅仅是将基因型与结果相关联时，它们就能捕捉到静态方法所遗漏的信息。

## Abstract
The same genome produces different phenotypes in different conditions--yet predictive models encode genotype once and treat each trait independently. Here we show that representing phenotype generation as a dynamic biological process transforms predictive accuracy across bacteria, fungi, animals and plants.

BioWorldModel learns how organisms interpret their genome: frozen gene embeddings (species context) modulated by individual variation pass through four biological process layers (regulation [-&gt;] expression [-&gt;] pathway [-&gt;] cellular) that respond to environment and time. A state-conditioned attention mechanism rereads this dynamic representation, predicting full multivariate trait distributions.

Without modification, the architecture achieves mean correlation r = 0.678 on 214 bacterial growth traits (207% better than ridge regression), r = 0.915 on 35 yeast fitness traits (167% better), r = 0.499 on 199 fly phenotypes in small-sample regime (760% better), and r = 0.995 on 36 rice traits (49% better). Ablations confirm that modeling biological process--not model size--drives performance. When neural architectures represent how biology generates phenotype rather than merely associating genotype with outcome, they capture what static methods miss.

---

## 论文详细总结（自动生成）

这是一份关于论文《BioWorldModel: a single architecture predicts phenotype from genotype across four kingdoms of life》的深度结构化总结：

### 1. 核心问题与整体含义（研究动机和背景）
论文的核心问题在于：**如何更准确地从基因型（Genotype）预测表型（Phenotype）？**
传统的基因组预测方法（如岭回归、随机森林）存在三大局限：
*   **静态假设**：将基因组视为静态编码，忽略了同一基因在不同环境和发育阶段会被“差异化解读”的生物学本质。
*   **性状独立**：通常独立预测每个性状，无法捕捉基因的多效性（Pleiotropy）。
*   **缺乏过程建模**：仅进行统计关联（Pattern Matching），而非模拟生物生成过程（Process Modeling）。
**研究动机**是构建一个能够模拟生物体如何根据环境和时间“解释”基因组的统一深度学习架构，从而提升跨物种的预测精度。

### 2. 方法论：核心思想与关键技术
BioWorldModel 的核心思想是将表型生成视为一个**动态的生物解释过程**。其架构包含四个创新点：
*   **因子化基因表示**：将基因表示分为两部分：$h_{ref}$（来自预训练模型 Evo 2 7B 的冻结进化上下文，代表“基因做什么”）和 $\delta h_i$（基于个体 SNP 特征学习到的调制信号，代表“个体有什么”）。
*   **BioProcessStack（生物过程栈）**：通过四个连续层模拟生物层级：**调控 $\rightarrow$ 表达 $\rightarrow$ 通路 $\rightarrow$ 细胞**。每一层都通过环境和时间信号进行门控调制，使同一基因组在不同条件下产生不同的动态表示。
*   **ReadGate（状态条件读取）**：利用注意力机制，根据生物体当前的状态、环境和记忆，从基因组向量中选择性地读取相关信息。
*   **四通道生物记忆**：设计了稳态（Homeostatic）、发育（Developmental）、偶发（Episodic）和群体（Population）四个记忆通道，捕捉不同时间尺度的生物学变化。
*   **多元分布输出**：使用 Cholesky 参数化预测完整的性状协方差矩阵，直接建模性状间的相关性。

### 3. 实验设计：数据集、Benchmark 与对比方法
研究在生命四大界的代表性生物上进行了验证，所有实验使用**完全相同的架构和超参数**：
*   **数据集**：
    1.  **细菌**（大肠杆菌）：214 种生长适应性性状。
    2.  **真菌**（酿酒酵母）：35 种适应性性状。
    3.  **动物**（黑腹果蝇）：199 种形态、行为和生活史性状（极小样本量 $N=41$）。
    4.  **植物**（水稻）：36 种农艺性状。
*   **对比基准（Benchmark）**：
    *   岭回归（GBLUP）、随机森林（Random Forest）、BayesB (ElasticNet)、Lasso 以及均值基准。
*   **评估指标**：Pearson 相关系数 $r$、均方根误差 (RMSE)、负对数似然 (NLL)、校准误差 (ECE) 等。

### 4. 资源与算力
论文明确记录了使用的算力资源：
*   **硬件**：4 $\times$ NVIDIA H100 GPU (80GB)。
*   **训练时长**：
    *   大肠杆菌：12 小时（500 步）。
    *   酵母：2 天（2000 步）。
    *   果蝇：3 小时（100 步，早停）。
    *   水稻：4 天（1000 步）。
*   **推理速度**：CPU 上每样本每步约 1-3 秒。

### 5. 实验数量与充分性
实验设计非常充分且具有说服力：
*   **跨界验证**：涵盖了从原核生物到高等真核生物的四个界，证明了架构的普适性。
*   **消融实验**：针对 E. coli 进行了 5 组消融实验，分别移除了生物过程栈、ReadGate、协方差建模、进化嵌入等，证实了每个生物学组件的独立贡献。
*   **不确定性分析**：通过 MC Dropout 分解了认识不确定性（模型）和偶然不确定性（噪声），验证了模型对自身预测局限性的感知能力。
*   **客观性**：基准模型经过了充分的超参数调优，而 BioWorldModel 在所有物种上保持参数固定，确保了对比的公平性。

### 6. 主要结论与发现
*   **性能飞跃**：BioWorldModel 在所有物种上均显著优于传统方法。在果蝇的小样本任务中提升高达 760%，在水稻任务中相关性接近饱和（$r=0.995$）。
*   **结构胜过规模**：消融实验显示，性能提升主要源于对生物过程的模拟（如环境调制层），而非单纯增加参数量。
*   **捕捉多效性**：模型能够成功恢复性状间的协方差结构（水稻中 $r=0.59$），证明其学习到了真实的生物学关联。
*   **小样本鲁棒性**：在数据极度匮乏的情况下，生物学先验结构能有效稳定学习过程。

### 7. 优点：亮点总结
*   **生物学一致性**：将“基因组解读”这一生物学事实转化为架构设计，而非黑盒拟合。
*   **引入进化先验**：巧妙利用冻结的大规模基因组基础模型（Evo 2）嵌入，引入了数百万年进化积累的知识。
*   **统一性**：一个架构无需针对物种微调即可通用，展示了“生物世界模型”的潜力。
*   **概率化输出**：不仅给出点预测，还提供不确定性和性状相关性，对育种决策更具参考价值。

### 8. 不足与局限
*   **校准度不一致**：虽然预测精度高，但在某些物种（如酵母和大肠杆菌）上存在过自信或欠自信的问题，概率分布的质量仍有提升空间。
*   **时间动态验证不足**：虽然架构支持时间序列，但目前测试的数据集多为单时间点快照，尚未在真正的纵向发育数据上充分验证。
*   **跨群体迁移待证**：目前主要在物种内进行训练和测试，跨地理种群或跨育种计划的“零样本”迁移能力尚在研究中。
*   **计算成本**：相比于简单的线性回归，该模型的训练和推理成本显著更高，可能限制其在某些资源受限场景下的应用。

（完）
