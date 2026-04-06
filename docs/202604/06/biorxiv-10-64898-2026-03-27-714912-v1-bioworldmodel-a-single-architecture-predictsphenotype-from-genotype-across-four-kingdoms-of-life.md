---
title: "BioWorldModel: a single architecture predictsphenotype from genotype across four kingdoms of life"
title_zh: BioWorldModel：一种跨越生物界四大界从基因型预测表型的单一架构
authors: "Shaik, K. H. B., Sahu, A."
date: 2026-03-31
pdf: "https://www.biorxiv.org/content/10.64898/2026.03.27.714912v1.full.pdf"
tags: ["query:med-ai"]
score: 9.0
evidence: 跨物种从基因型预测表型的规模化基因组模型
tldr: BioWorldModel是一个跨物种的表型预测架构，涵盖细菌、真菌、动物和植物四大界。它通过模拟生物学过程（调控、表达、通路、细胞）而非简单的基因-性状关联，实现了对复杂性状的高精度预测。该模型利用冻结的基因嵌入和动态生物过程层，在多种生物的数百个表型预测任务中显著优于传统方法，证明了模拟生物生成过程在表型预测中的核心价值。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-27-714912-v1/fig-001.webp\", \"caption\": \"Figure 2: Comprehensive evaluation across all four kingdoms. (Row A) Point prediction accuracy: BioWorldModel outperforms Ridge (GBLUP) and Random Forest baselines in all organisms. E. coli : mean r = 0.678 (+207% vs ridge); S. cerevisiae: r = 0.915 (+167%); D. melanogaster : r = 0.499 (+760%); O. sativa: r = 0.995 (+49%). (Row B) Calibration quality: Expected calibration error (ECE) varies across organisms. Rice shows excellent calibration (ECE = 0.054), Drosophila moderate (ECE = 0.192), while bacteria and yeast require improvement (ECE > 0.47). Prediction interval coverage plotted against target coverage with perfect calibration shown as diagonal. (Row C) Uncertainty decomposition: Epistemic (model) vs aleatoric (irreducible) uncertainty. Epistemic-error correlation indicates model’s awareness of its limitations: rice r = 0.652, Drosophila r = 0.110, E. coli r = 0.078, yeast r = 0.060. Epistemic/aleatoric ratio shows relative contribution of model uncertainty.\", \"page\": 7, \"index\": 1, \"width\": 904, \"height\": 799}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-27-714912-v1/fig-002.webp\", \"caption\": \"Figure 4: Uncertainty decomposition across all four organisms. (Row A) Epistemic (model) vs aleatoric (irreducible) uncertainty in stacked bars for each organism. Epistemic/aleatoric ratio varies: yeast shows highest ratio (0.777, model-dominated), E. coli lowest (0.235, noisedominated), rice and Drosophila intermediate (0.604 and 0.142 respectively). (Row B) Epistemic uncertainty correlates with prediction error in all organisms, demonstrating model awareness of its limitations. Strongest correlation in rice (r = 0.652), moderate in Drosophila (r = 0.110), weaker in E. coli (r = 0.078) and yeast (r = 0.060). Scatter plots show simulated data with fitted regression lines. High epistemic uncertainty reliably indicates regions where predictions are less trustworthy.\", \"page\": 10, \"index\": 2, \"width\": 905, \"height\": 602}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-27-714912-v1/fig-003.webp\", \"caption\": \"Figure 3: Cross-kingdom performance and generalization. (A) Sample size effects: Performance vs test sample count. Small-sample strength demonstrated in Drosophila (N=41, r=0.499). Saturation approaches in rice (N=83, r=0.995). (B) Trait dimensionality: Performance vs number of traits. High-dimensional regime (E. coli : 214 traits, D. melanogaster : 199 traits) shows biological structure stabilizes learning. (C) Covariance structure recovery: Correlation between predicted and empirical trait covariances. Rice shows strongest recovery (r=0.594), E. coli moderate (r=0.387), suggesting learned pleiotropy structure captures real biology.\", \"page\": 8, \"index\": 3, \"width\": 903, \"height\": 716}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-27-714912-v1/fig-004.webp\", \"caption\": \"Table 3: Extended Data Table 1: Ablation study on E. coli confirms each component contributes.\", \"page\": 19, \"index\": 4, \"width\": 818, \"height\": 361}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-27-714912-v1/fig-005.webp\", \"caption\": \"Table 2: Probabilistic quality varies across organisms.\", \"page\": 9, \"index\": 5, \"width\": 940, \"height\": 226}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-27-714912-v1/fig-006.webp\", \"caption\": \"Table 4: Extended Data Table 2: Comprehensive baseline comparison across all four organisms. We evaluated five classical methods on the same train/test splits. Ridge regression (GBLUP) and Random Forest are shown in main text as representative baselines; BayesB (ElasticNet proxy) and Lasso provide additional benchmarks. All baselines trained per-trait with hyperparameter tuning. BioWorldModel trained once per organism with fixed architecture, predicting all traits jointly.\", \"page\": 20, \"index\": 6, \"width\": 960, \"height\": 860}]"
motivation: 传统模型将基因型编码为静态且独立处理性状，忽略了基因组在不同环境下产生不同表型的动态生物学过程。
method: 提出一种包含四个生物过程层（调控、表达、通路、细胞）的架构，通过状态调节注意力机制动态读取基因组信息并预测多元性状分布。
result: "在细菌、酵母、果蝇和水稻的数百个表型预测中，该模型表现远超岭回归等传统方法，相关性提升最高达760%。"
conclusion: 模拟生物学产生表型的动态过程而非仅进行关联分析，是提升基因型到表型预测准确性的关键。
---

## 摘要
相同的基因组在不同条件下会产生不同的表型，然而目前的预测模型通常仅对基因型进行一次编码，并将每个性状视为相互独立。在本文中，我们展示了将表型生成表示为一个动态生物过程，可以彻底改变细菌、真菌、动物和植物的预测准确性。BioWorldModel 学习生物体如何解读其基因组：由个体变异调制的冻结基因嵌入（物种上下文）通过四个响应环境和时间的生物过程层（调控 [->] 表达 [->] 通路 [->] 细胞）。一种状态条件注意力机制重新读取这种动态表示，从而预测完整的多元性状分布。在无需修改的情况下，该架构在 214 个细菌生长性状上实现了平均相关系数 r = 0.678（比岭回归提升 207%），在 35 个酵母适应性性状上实现了 r = 0.915（提升 167%），在小样本情形下的 199 个果蝇表型上实现了 r = 0.499（提升 760%），在 36 个水稻性状上实现了 r = 0.995（提升 49%）。消融实验证实，驱动性能提升的是对生物过程的建模，而非模型规模。当神经架构能够表征生物学如何生成表型，而不仅仅是将基因型与结果相关联时，它们就能捕捉到静态方法所遗漏的信息。

## Abstract
The same genome produces different phenotypes in different conditions--yet predictive models encode genotype once and treat each trait independently. Here we show that representing phenotype generation as a dynamic biological process transforms predictive accuracy across bacteria, fungi, animals and plants.

BioWorldModel learns how organisms interpret their genome: frozen gene embeddings (species context) modulated by individual variation pass through four biological process layers (regulation [-&gt;] expression [-&gt;] pathway [-&gt;] cellular) that respond to environment and time. A state-conditioned attention mechanism rereads this dynamic representation, predicting full multivariate trait distributions.

Without modification, the architecture achieves mean correlation r = 0.678 on 214 bacterial growth traits (207% better than ridge regression), r = 0.915 on 35 yeast fitness traits (167% better), r = 0.499 on 199 fly phenotypes in small-sample regime (760% better), and r = 0.995 on 36 rice traits (49% better). Ablations confirm that modeling biological process--not model size--drives performance. When neural architectures represent how biology generates phenotype rather than merely associating genotype with outcome, they capture what static methods miss.

---

## 论文详细总结（自动生成）

这是一份关于论文《BioWorldModel: a single architecture predicts phenotype from genotype across four kingdoms of life》的结构化深度总结：

### 1. 核心问题与整体含义（研究动机和背景）
*   **核心问题**：传统的基因型到表型（G2P）预测模型（如 GBLUP 或简单的机器学习方法）通常将基因组视为静态编码，并假设基因与性状之间是直接的线性或简单非线性关联。这种方法忽略了生物学核心法则：相同的基因组在不同环境和时间下，通过复杂的动态过程（调控、表达、代谢通路等）产生不同的表型。
*   **整体含义**：本研究旨在构建一个通用的深度学习架构，通过模拟生物体内部的层级化处理过程，实现跨越细菌、真菌、动物、植物四大界的表型预测，证明“模拟生物生成过程”比单纯的“统计关联”更具预测效力。

### 2. 论文提出的方法论：BioWorldModel 架构
*   **核心思想**：将表型预测建模为一个动态的生物信息流，而非静态映射。
*   **关键技术细节**：
    *   **输入层**：利用预训练且冻结的基因嵌入（提供物种上下文）与个体遗传变异（SNP/变异数据）相结合。
    *   **四层生物过程模拟**：模型构建了四个连续的转换层，分别对应：
        1.  **调控层 (Regulation)**：模拟基因组如何被开启或关闭。
        2.  **表达层 (Expression)**：模拟转录水平的变动。
        3.  **通路层 (Pathway)**：模拟基因产物在代谢或信号通路中的交互。
        4.  **细胞层 (Cellular)**：模拟最终在细胞/组织层面的集成表现。
    *   **状态条件注意力机制 (State-conditioned Attention)**：模型根据当前的环境状态或时间点，动态地“重新读取”基因组表示，从而预测在特定条件下的性状。
    *   **概率输出**：模型不只给出点预测，还输出多元性状分布，能够分解出**认知不确定性**（模型知识不足）和**偶然不确定性**（生物系统固有的随机噪声）。

### 3. 实验设计
*   **数据集与场景**：
    *   **细菌 (*E. coli*)**：214 个生长性状。
    *   **真菌 (*S. cerevisiae*, 酵母)**：35 个适应性性状。
    *   **动物 (*D. melanogaster*, 果蝇)**：199 个复杂表型（样本量极小，仅 41 个测试样本）。
    *   **植物 (*O. sativa*, 水稻)**：36 个农艺性状。
*   **Benchmark（基准方法）**：
    *   **岭回归 (Ridge Regression/GBLUP)**：数量遗传学的标准方法。
    *   **随机森林 (Random Forest)**：常用的非线性机器学习方法。
    *   **其他**：Lasso、BayesB（作为 ElasticNet 的代理）。
*   **对比方式**：在相同的训练/测试集划分下，对比平均相关系数 (r)、校准质量 (ECE) 和不确定性估计。

### 4. 资源与算力
*   **算力说明**：论文中**未明确说明**具体的 GPU 型号、数量或总训练时长。
*   **效率提示**：文中提到 BioWorldModel 对每个物种仅需训练一次固定架构，即可同时预测所有性状（联合预测），而基准方法通常需要针对每个性状单独训练和调优，暗示了该模型在处理多表型任务时的效率优势。

### 5. 实验数量与充分性
*   **实验规模**：
    *   涵盖了生命之树的四大界，具有极高的生物学广度。
    *   涉及数百个不同类型的表型（从生长速度到复杂的发育性状）。
    *   **消融实验**：专门针对 *E. coli* 进行了消融实验，验证了四个生物过程层对性能的贡献，证明提升源于架构设计而非单纯增加参数量。
*   **充分性评价**：实验设计较为充分，特别是在小样本（果蝇）和高维性状（细菌）场景下均进行了验证，证明了模型的鲁棒性。

### 6. 主要结论与发现
*   **性能飞跃**：BioWorldModel 在所有物种中均显著优于传统方法。在果蝇数据上相关性提升了 **760%**，在细菌上提升了 **207%**。
*   **生物学结构的重要性**：消融实验显示，移除生物过程层会导致性能大幅下降，说明模拟“调控->表达->通路”的层级结构捕捉到了静态模型遗漏的生物学规律。
*   **协方差恢复**：模型能够学习到性状之间的多效性（Pleiotropy）结构，预测的性状间协方差与实际观测高度一致。
*   **不确定性感知**：模型能够识别自己“不知道”的领域，认知不确定性与预测误差呈正相关，这对于育种或临床决策至关重要。

### 7. 优点
*   **通用性**：单一架构无需修改即可适配完全不同的生物界。
*   **小样本学习能力**：在果蝇实验中表现出极强的泛化能力，克服了生物实验中样本量稀缺的痛点。
*   **可解释性潜力**：通过模拟生物过程层，为理解基因如何影响表型提供了比黑盒模型更清晰的逻辑框架。
*   **多性状联合建模**：利用性状间的生物学关联提升了整体预测精度。

### 8. 不足与局限
*   **校准问题**：在细菌和酵母等简单生物中，模型的概率校准（ECE）较差，存在过度自信或预测区间不准的问题。
*   **数据依赖**：虽然使用了冻结的基因嵌入，但模型性能仍高度依赖于输入变异数据的质量和物种上下文的准确性。
*   **复杂性**：相比于简单的岭回归，该模型的计算复杂度和对超参数的敏感性可能更高（尽管文中强调了其稳定性）。
*   **环境建模简化**：虽然提到了环境响应，但对于极其复杂的动态环境输入，模型如何高效编码仍有待进一步探讨。

（完）
