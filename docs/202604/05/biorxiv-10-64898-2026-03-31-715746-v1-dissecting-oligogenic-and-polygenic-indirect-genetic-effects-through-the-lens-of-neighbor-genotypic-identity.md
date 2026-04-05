---
title: Dissecting oligogenic and polygenic indirect genetic effects through the lens of neighbor genotypic identity
title_zh: 从邻体基因型一致性的视角剖析寡基因和多基因间接遗传效应
authors: "Sato, Y., Hamazaki, K."
date: 2026-04-03
pdf: "https://www.biorxiv.org/content/10.64898/2026.03.31.715746v1.full.pdf"
tags: ["query:gwas"]
score: 9.0
evidence: 间接遗传效应的 GWAS 和基因组预测统一方法
tldr: 该研究探讨了个体表型受邻居基因型影响的间接遗传效应（IGE）。作者开发了一种基于铁磁学伊辛模型的多核混合模型，将多基因和寡基因IGE整合，简化了全基因组关联分析（GWAS）和基因组预测（GP）的实现。通过对杨树、苹果和葡萄三种木本植物的分析，揭示了种内竞争的遗传基础，并识别了影响苹果树干生长的关键变异，为解析群体表现的遗传结构提供了新工具。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-31-715746-v1/fig-001.webp\", \"caption\": \"Figures 528\", \"page\": 19, \"index\": 1, \"width\": 852, \"height\": 594}]"
motivation: 现有的间接遗传效应研究缺乏统一的方法来同时处理多基因和寡基因效应，限制了对群体遗传结构的深入解析。
method: 提出一种基于伊辛模型的多核混合模型，通过单一协方差参数整合邻居基因型一致性，实现对IGE的GWAS和GP分析。
result: 模拟显示该模型能有效推断直接与间接遗传效应间的权衡，并在杨树和苹果中发现显著的种内竞争效应及相关遗传变异。
conclusion: 该研究提供了一个灵活的分析框架，为理解植物间相互作用及其对群体生产力的遗传贡献提供了有效工具。
---

## 摘要
个体表型通常取决于群体内其他个体的基因型。这些现象被称为“间接遗传效应”（IGEs），并已通过数量遗传模型与直接遗传效应（DGEs）区分开来。近期的研究利用高分辨率多态性数据实现了 IGEs 的基因组预测（GP）和全基因组关联分析（GWAS），但统一的方法仍然有限。在本文中，我们使用一种包含两个随机效应且具有单一协方差参数的多核混合模型，整合了多基因和寡基因 IGEs。在该实现的基础上，铁磁学的伊辛模型（Ising model）使我们能够分别简化用于 GWAS 和 GP 的位点级和背景 IGEs。我们的模拟表明，虽然先前模型与本模型表现相似，但本模型可以推断 DGEs 和 IGEs 之间的权衡。通过将该方法应用于三种木本植物，我们在杨树和苹果树中发现了基因型间竞争的证据，但在攀缘葡萄藤中证据有限。基于 GWAS，我们还检测到了与苹果树干生长的竞争性 IGEs 相关的显著变异。我们的研究为 IGEs 的 GWAS/GP 提供了一种灵活的实现方式，从而为剖析群体表现的遗传结构提供了有效工具。

## Abstract
Individual phenotypes often depend on the genotypes of other individuals within a group. These phenomena are termed 'indirect genetic effects' (IGEs) and have been distinguished from direct genetic effects (DGEs) using quantitative genetic models. Recent studies have utilized high-resolution polymorphism data to enable genomic prediction (GP) and genome-wide association study (GWAS) of IGEs, but unified methods remain limited. Here we integrate polygenic and oligogenic IGEs using a multi-kernel mixed model incorporating two random effects with a single covariance parameter. Underlying this implementation, the Ising model of ferromagnetics enabled us to simplify locus-wise and background IGEs for GWAS and GP, respectively. Our simulations demonstrated that, while the previous and present models exhibited similar performance, the present model can infer a trade-off between DGEs and IGEs. By applying this method to three species of woody plants, we found evidence for intergenotypic competition in aspen and apple trees, but limited evidence in climbing grapevines. Based on GWAS, we also detected significant variants associated with the competitive IGEs on the apple trunk growth. Our study offers a flexible implementation for GWAS/GP of IGEs, thereby providing an effective tool to dissect the genetic architecture of group performance.

---

## 论文详细总结（自动生成）

这篇论文题为《从邻体基因型一致性的视角剖析寡基因和多基因间接遗传效应》，由日本北海道大学和千叶大学的研究人员合作完成。以下是对该论文的结构化总结：

### 1. 核心问题与整体含义（研究动机和背景）
*   **核心问题**：如何在一个统一的框架下，同时解析复杂性状中的**直接遗传效应（DGEs）**和**间接遗传效应（IGEs）**（即个体表型受邻居基因型影响的现象）。
*   **研究动机**：IGEs 对进化轨迹和动植物育种至关重要，但现有的基因组预测（GP）和全基因组关联分析（GWAS）方法往往将多基因背景效应与单位点效应割裂开来。
*   **整体含义**：通过引入物理学中的**伊辛模型（Ising model）**，研究者试图建立一种能够同时处理多基因（背景）和寡基因（位点级）效应的灵活模型，以揭示个体与群体表现之间的遗传权衡（如竞争或协作）。

### 2. 方法论：核心思想与技术细节
*   **核心思想**：将邻居间的基因型相互作用类比为铁磁学中磁体偶极子的相互作用（伊辛模型）。
*   **关键技术细节**：
    *   **多核混合模型**：构建了一个包含两个随机效应（DGE 和 IGE）的线性混合模型。
    *   **协方差参数 ($\rho_{12}$)**：引入单一协方差参数来捕捉 DGE 和 IGE 之间的相关性。正相关代表协同，负相关代表竞争。
    *   **固定效应建模**：在 GWAS 中，模型定义了三个系数：$\beta_{q,s}$（位点级 DGE）、$\beta_{q,n}$（邻域等位基因频率偏差）和 $\beta_{q,s \times n}$（基于邻体相似性的位点级 IGE）。
    *   **算法实现**：整合了作者此前开发的 **RAINBOW** 算法（用于优化权重）和 **rNeighborGWAS** 软件包，通过限制最大似然法（REML）求解方差分量。

### 3. 实验设计
*   **数据集/场景**：
    1.  **模拟数据**：基于 SLiM 软件生成的 30 组独立基因组数据，模拟了不同强度的 DGE-IGE 协方差（$\rho = 0, \pm 0.3, \pm 0.6$）。
    2.  **真实木本植物数据**：
        *   **颤杨 (WisAsp)**：800+ 个体，16.9万个 SNP，涉及 18 种性状。
        *   **苹果 (REFPOP)**：欧洲 6 个地点、2万+ 个体、534 个品种，涉及 30 种性状。
        *   **葡萄 (INNOVINE)**：3642 个体，9万个 SNP，涉及 19 种性状。
*   **Benchmark 与对比**：
    *   对比了包含与不包含协方差参数 $\rho_{12}$ 的模型表现。
    *   使用 $R^2$（决定系数）和 MAE（平均绝对误差）评估预测准确性；使用 ROC 曲线和 AUC 评估 GWAS 的检测效力。

### 4. 资源与算力
*   **算力说明**：论文提到计算资源由东京大学医科学研究所的人类基因组中心（Shirokane 超级计算机）提供。
*   **具体细节**：文中未明确列出具体的 GPU/CPU 核心数量、内存占用或具体的训练时长。

### 5. 实验数量与充分性
*   **实验规模**：
    *   模拟实验进行了 30 次独立迭代，覆盖了从负相关到正相关的多种遗传架构场景。
    *   应用实验涵盖了三种具有不同生长习性的木本植物（乔木与攀缘植物），并跨越了多个年份和地理环境。
*   **充分性与公平性**：实验设计较为充分。通过 10 折交叉验证评估 GP 表现，并使用 FDR（错误发现率）控制 GWAS 的假阳性。模拟实验验证了模型在已知真值情况下的参数估计能力，确保了后续真实数据分析的客观性。

### 6. 主要结论与发现
*   **模型效能**：在 DGE 和 IGE 正相关时，包含协方差参数能显著提升基因组预测的准确性；但在负相关（竞争）时，估计稳定性略有下降。
*   **生物学发现**：
    *   **竞争证据**：在杨树和苹果中发现了显著的负 DGE-IGE 协方差，且这种竞争效应随树木生长（树干直径增加）而增强。
    *   **性状差异**：生长相关性状（如树干增量）受 IGE 影响较大，而物候性状（如开花时间）主要受 DGE 控制。
    *   **关键位点**：在苹果中识别出 7 号染色体上与树干生长竞争相关的显著 IGE SNP，涉及蛋白激酶等候选基因。
    *   **葡萄特例**：攀缘葡萄藤中几乎未检测到邻体竞争，可能与其垂直生长习性和较大的种植间距有关。

### 7. 优点
*   **理论创新**：巧妙地将物理学伊辛模型引入数量遗传学，为邻体相互作用提供了直观的数学解释。
*   **功能全面**：一个模型同时实现了方差组分剖析、基因组预测（GP）和关联分析（GWAS）。
*   **实用性强**：提供了开源 R 软件包（`rNeighborLMM`），方便其他研究者在林业、农业甚至动物社会行为研究中应用。

### 8. 不足与局限
*   **负协方差估计难题**：当 $\rho_{12}$ 为负值时，加权核矩阵可能非正定，需进行近似处理，这限制了模型在极端竞争场景下的精度。
*   **空间尺度依赖**：模型假设 IGE 仅来自最近邻个体，但在自然界中，相互作用的范围可能更广或具有复杂的距离衰减特性。
*   **计算复杂性**：多核混合模型的参数估计比传统单核模型更耗时，在大规模群体数据上的扩展性仍有待观察。

（完）
