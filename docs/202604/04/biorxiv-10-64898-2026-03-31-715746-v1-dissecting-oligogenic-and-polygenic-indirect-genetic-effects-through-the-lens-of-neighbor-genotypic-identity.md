---
title: Dissecting oligogenic and polygenic indirect genetic effects through the lens of neighbor genotypic identity
title_zh: 从邻体基因型一致性的视角剖析寡基因和多基因间接遗传效应
authors: "Sato, Y., Hamazaki, K."
date: 2026-04-03
pdf: "https://www.biorxiv.org/content/10.64898/2026.03.31.715746v1.full.pdf"
tags: ["query:gwas"]
score: 9.0
evidence: 间接遗传效应的GWAS和基因组预测统一方法
tldr: 该研究针对间接遗传效应（IGEs）缺乏统一分析方法的问题，提出了一种基于铁磁学伊辛模型的多核混合模型。该方法整合了多基因和寡基因IGEs，能够同时进行基因组预测（GP）和全基因组关联分析（GWAS）。通过对杨树、苹果和葡萄等木本植物的实证研究，揭示了种内竞争的遗传基础，并发现了影响苹果树干生长的显著变异位点，为解析群体表现的遗传结构提供了灵活有效的工具。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-31-715746-v1/fig-001.webp\", \"caption\": \"Figures 528\", \"page\": 19, \"index\": 1, \"width\": 852, \"height\": 594}]"
motivation: 旨在解决现有研究中缺乏统一方法来同时处理和分析多基因与寡基因间接遗传效应（IGEs）的问题。
method: 借鉴物理学中的伊辛模型，开发了一种包含两个随机效应且具有单一协方差参数的多核混合模型，用于简化IGEs的GWAS和GP分析。
result: 模拟显示该模型能有效推断直接与间接遗传效应间的权衡，并在苹果和杨树中发现了显著的种内竞争证据及相关遗传变异。
conclusion: 该研究提供了一个灵活的IGEs分析框架，有助于深入理解植物群体表现的遗传架构及个体间的相互作用。
---

## 摘要
个体表型通常取决于群体内其他个体的基因型。这些现象被称为“间接遗传效应”（IGEs），并已通过数量遗传模型与直接遗传效应（DGEs）区分开来。近期的研究利用高分辨率多态性数据实现了 IGEs 的基因组预测（GP）和全基因组关联分析（GWAS），但统一的方法仍然有限。在本文中，我们使用包含两个随机效应且具有单一协方差参数的多核混合模型，整合了多基因和寡基因 IGEs。在该实现的基础上，铁磁学的伊辛模型（Ising model）使我们能够分别简化用于 GWAS 和 GP 的位点级和背景 IGEs。我们的模拟表明，虽然先前模型与当前模型表现相似，但当前模型可以推断 DGEs 和 IGEs 之间的权衡。通过将该方法应用于三种木本植物，我们在杨树和苹果树中发现了基因型间竞争的证据，但在攀缘葡萄藤中证据有限。基于 GWAS，我们还检测到了与苹果树干生长的竞争性 IGEs 相关的显著变异。我们的研究为 IGEs 的 GWAS/GP 提供了一种灵活的实现方式，从而为剖析群体表现的遗传结构提供了有效的工具。

## Abstract
Individual phenotypes often depend on the genotypes of other individuals within a group. These phenomena are termed 'indirect genetic effects' (IGEs) and have been distinguished from direct genetic effects (DGEs) using quantitative genetic models. Recent studies have utilized high-resolution polymorphism data to enable genomic prediction (GP) and genome-wide association study (GWAS) of IGEs, but unified methods remain limited. Here we integrate polygenic and oligogenic IGEs using a multi-kernel mixed model incorporating two random effects with a single covariance parameter. Underlying this implementation, the Ising model of ferromagnetics enabled us to simplify locus-wise and background IGEs for GWAS and GP, respectively. Our simulations demonstrated that, while the previous and present models exhibited similar performance, the present model can infer a trade-off between DGEs and IGEs. By applying this method to three species of woody plants, we found evidence for intergenotypic competition in aspen and apple trees, but limited evidence in climbing grapevines. Based on GWAS, we also detected significant variants associated with the competitive IGEs on the apple trunk growth. Our study offers a flexible implementation for GWAS/GP of IGEs, thereby providing an effective tool to dissect the genetic architecture of group performance.

---

## 论文详细总结（自动生成）

以下是对论文《Dissecting oligogenic and polygenic indirect genetic effects through the lens of neighbor genotypic identity》的结构化深入总结：

### 1. 核心问题与整体含义（研究动机和背景）
论文探讨的核心问题是如何在统一的统计框架下，同时解析**直接遗传效应（DGEs）**与**间接遗传效应（IGEs）**。
*   **背景**：个体的表型不仅受自身基因型影响，还受到群体内邻居基因型的影响（即 IGEs，也称社会遗传效应）。这在植物育种（如种植密度优化）和进化生物学中至关重要。
*   **动机**：尽管已有研究利用高密度 SNP 数据进行 IGEs 的全基因组关联分析（GWAS）和基因组预测（GP），但目前缺乏一种能够灵活整合“多基因背景效应”（Polygenic）和“主效/寡基因位点效应”（Oligogenic）的统一模型，且难以量化 DGE 和 IGE 之间的遗传权衡（Trade-off）。

### 2. 论文提出的方法论
作者开发了一种基于**多核混合线性模型（Multi-kernel Mixed Model）**的新方法，其核心思想借鉴了物理学中的**伊辛模型（Ising Model）**：
*   **核心思想**：将邻居间的基因型相互作用类比为铁磁学中磁偶极子间的相互作用。通过计算邻体间的基因型一致性（Similarity），将复杂的生物交互简化为可计算的统计项。
*   **关键技术细节**：
    *   **固定效应**：在 GWAS 中，模型包含三个系数：$\beta_s$（自身效应）、$\beta_n$（邻居频率效应）和 $\beta_{s \times n}$（自身与邻居的交互效应，即基于伊辛模型的相似性得分）。
    *   **随机效应**：在 GP 中，使用两个随机效应项分别代表多基因 DGE 和 IGE，并引入一个关键的**协方差参数 $\rho_{12}$**。
    *   **算法流程**：利用 **RAINBOWR** 算法优化不同核矩阵（Kinship matrices）的权重，通过似然比检验（LRT）确定 IGE 的显著性，并利用特征值分解提高计算效率。

### 3. 实验设计
研究采用了“模拟验证 + 实证应用”的双重设计：
*   **模拟实验**：基于 SLiM 软件生成的 30 组独立基因组数据，模拟了不同强度和方向（正向/负向）的 DGE-IGE 协方差场景。
*   **实证数据集**：
    1.  **颤杨（WisAsp 项目）**：800+ 个体，16.9万个 SNPs，涵盖生长、物候和防御化学性状。
    2.  **苹果（REFPOP 项目）**：欧洲 6 个地点、2万+ 个体、534 个品种、28.1万个 SNPs，关注产量与生长性状。
    3.  **葡萄（INNOVINE 项目）**：3642 个个体、9万个 SNPs，涉及果实品质和生长。
*   **Benchmark**：对比了包含与不包含协方差参数 $\rho$ 的模型表现，评估其在参数估计准确度、预测能力（$R^2$）和 GWAS 检出率（AUC/敏感度）上的差异。

### 4. 资源与算力
*   **算力说明**：论文明确提到计算资源由**东京大学人类基因组中心（Human Genome Center）的超级计算机系统（Shirokane）**提供。
*   **具体细节**：文中未详细列出具体的 GPU/CPU 型号、核心数量或具体的训练总时长。但考虑到处理 2.8万个体和 28万 SNPs 的多核混合模型计算量巨大，该研究依赖于高性能计算集群。

### 5. 实验数量与充分性
*   **实验数量**：模拟实验进行了 30 次独立迭代；实证部分涵盖了 3 种不同生长习性的木本植物（乔木 vs 攀缘植物），苹果数据集跨越了多个年份和地理环境。
*   **充分性与公平性**：
    *   **充分性**：实验设计考虑了正负协方差的多种可能性，并进行了 10 折交叉验证。
    *   **公平性**：通过与传统不含协方差的模型进行对比，客观展示了新模型在不同场景下的优劣（例如在负协方差下预测能力的局限性）。

### 6. 论文的主要结论与发现
*   **模型效能**：新模型能有效估计 DGE 和 IGE 之间的协方差方向。在 DGE-IGE 正相关时，引入协方差参数能显著提升基因组预测的准确性。
*   **生物学发现**：
    *   **竞争证据**：在杨树和苹果中发现了显著的负遗传协方差，表明存在强烈的种内竞争。
    *   **动态变化**：苹果树的竞争性 IGE 随树龄和树干直径增加而显著增强。
    *   **GWAS 成果**：在苹果第 7 号染色体上发现了与树干生长竞争相关的显著 QTL 位点，并定位到了如蛋白激酶超家族蛋白等候选基因。
    *   **特例**：攀缘植物（葡萄）的 IGE 较弱，可能与其垂直生长习性减少了水平邻里竞争有关。

### 7. 优点
*   **理论创新**：首次将物理学伊辛模型与多核混合模型结合，为 IGEs 提供了一个优雅且具有生物学解释力的数学框架。
*   **功能统一**：一个模型同时实现了 GWAS（定位主效位点）和 GP（评估全基因组贡献），提高了分析效率。
*   **工具可用性**：提供了开源 R 包 `rNeighborLMM` 和详细的在线教程，便于其他研究者复现。

### 8. 不足与局限
*   **数值稳定性**：当 DGE-IGE 协方差为负时，加权核矩阵可能非正定，虽然通过“最近正定矩阵近似”处理，但会导致参数估计波动较大。
*   **空间尺度依赖**：模型高度依赖于对“邻居”定义的准确性（如距离阈值），若空间元数据不全或交互范围设定错误，模型效能会大幅下降。
*   **计算复杂性**：多核模型在大规模群体（数万个体以上）中的计算开销依然较高，对内存和算法优化有极高要求。

（完）
