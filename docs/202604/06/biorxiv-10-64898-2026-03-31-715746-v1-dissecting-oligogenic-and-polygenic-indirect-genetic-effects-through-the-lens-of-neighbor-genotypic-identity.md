---
title: Dissecting oligogenic and polygenic indirect genetic effects through the lens of neighbor genotypic identity
title_zh: 从邻体基因型一致性的视角剖析寡基因和多基因间接遗传效应
authors: "Sato, Y., Hamazaki, K."
date: 2026-04-03
pdf: "https://www.biorxiv.org/content/10.64898/2026.03.31.715746v1.full.pdf"
tags: ["query:gwas"]
score: 10.0
evidence: 使用多核混合模型进行间接遗传效应的GWAS和基因组预测的统一方法
tldr: 该研究针对间接遗传效应（IGEs）缺乏统一分析方法的问题，提出一种基于伊辛模型的多核混合模型，整合了多基因和寡基因IGEs。该方法可同时进行基因组预测和关联分析，揭示了木本植物间的竞争性遗传效应及其与直接效应的权衡，为解析群体表现的遗传结构提供了有效工具。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-31-715746-v1/fig-001.webp\", \"caption\": \"Figures 528\", \"page\": 19, \"index\": 1, \"width\": 852, \"height\": 594}]"
motivation: 旨在解决现有研究中缺乏统一方法来同时处理和分析多基因及寡基因间接遗传效应（IGEs）的问题。
method: 借鉴物理学中的伊辛模型，开发了一种集成多核混合模型，通过单一协方差参数简化了位点特异性和背景IGEs的计算。
result: 模拟显示该模型能有效推断直接与间接遗传效应间的权衡，并在苹果和杨树中发现了显著的种内竞争效应及相关遗传变异。
conclusion: 该研究为解析群体水平下的遗传架构提供了灵活且高效的GWAS/GP工具，有助于深入理解生物个体间的遗传相互作用。
---

## 摘要
个体表型通常取决于群体内其他个体的基因型。这些现象被称为“间接遗传效应”（IGEs），并已通过数量遗传模型与直接遗传效应（DGEs）区分开来。近期的研究利用高分辨率多态性数据实现了 IGEs 的基因组预测（GP）和全基因组关联分析（GWAS），但统一的方法仍然有限。在本研究中，我们利用包含两个随机效应且具有单一协方差参数的多核混合模型，整合了多基因和寡基因 IGEs。在该实现的基础上，铁磁学的伊辛模型（Ising model）使我们能够分别简化用于 GWAS 和 GP 的位点级和背景 IGEs。我们的模拟表明，虽然先前模型与本模型表现相似，但本模型可以推断 DGEs 与 IGEs 之间的权衡。通过将该方法应用于三种木本植物，我们发现了杨树和苹果树中存在基因型间竞争的证据，但在攀缘葡萄藤中证据有限。基于 GWAS，我们还检测到了与苹果树干生长的竞争性 IGEs 相关的显著变异位点。我们的研究为 IGEs 的 GWAS/GP 提供了一种灵活的实现方式，从而为剖析群体表现的遗传结构提供了有效工具。

## Abstract
Individual phenotypes often depend on the genotypes of other individuals within a group. These phenomena are termed 'indirect genetic effects' (IGEs) and have been distinguished from direct genetic effects (DGEs) using quantitative genetic models. Recent studies have utilized high-resolution polymorphism data to enable genomic prediction (GP) and genome-wide association study (GWAS) of IGEs, but unified methods remain limited. Here we integrate polygenic and oligogenic IGEs using a multi-kernel mixed model incorporating two random effects with a single covariance parameter. Underlying this implementation, the Ising model of ferromagnetics enabled us to simplify locus-wise and background IGEs for GWAS and GP, respectively. Our simulations demonstrated that, while the previous and present models exhibited similar performance, the present model can infer a trade-off between DGEs and IGEs. By applying this method to three species of woody plants, we found evidence for intergenotypic competition in aspen and apple trees, but limited evidence in climbing grapevines. Based on GWAS, we also detected significant variants associated with the competitive IGEs on the apple trunk growth. Our study offers a flexible implementation for GWAS/GP of IGEs, thereby providing an effective tool to dissect the genetic architecture of group performance.

---

## 论文详细总结（自动生成）

以下是对论文《从邻体基因型一致性的视角剖析寡基因和多基因间接遗传效应》（Dissecting oligogenic and polygenic indirect genetic effects through the lens of neighbor genotypic identity）的结构化深入总结：

### 1. 核心问题与整体含义（研究动机和背景）
*   **核心问题**：个体的表型不仅受自身基因型（直接遗传效应，DGEs）影响，还受群体内邻体基因型（间接遗传效应，IGEs）的影响。尽管已有研究利用高密度 SNP 数据对 IGEs 进行全基因组关联分析（GWAS）和基因组预测（GP），但目前缺乏一个能够同时整合**多基因**（背景效应）和**寡基因**（位点特异性效应）IGEs 的统一、灵活的统计框架。
*   **研究动机**：在植物和动物育种中，理解 DGEs 和 IGEs 之间的协同或竞争关系（权衡）对于优化群体表现至关重要。作者旨在开发一种新模型，通过空间邻体基因型的一致性来解析这种复杂的遗传架构。

### 2. 论文提出的方法论
*   **核心思想**：借鉴物理学中描述磁体相互作用的**伊辛模型（Ising model）**，将邻体间的基因型相互作用类比为磁极间的物理作用。
*   **关键技术细节**：
    *   **多核混合模型**：构建了一个包含两个随机效应（DGE 和 IGE）的线性混合模型。
    *   **协方差参数 ($\rho_{12}$)**：引入单一协方差参数来捕捉 DGEs 和 IGEs 之间的相关性。正值表示协同，负值表示竞争。
    *   **固定效应与随机效应**：
        *   **固定效应**：用于 GWAS，定义了位点级的自效应、邻体效应及其交互项。
        *   **随机效应**：用于 GP，利用基于邻体基因型相似性加权的亲缘关系矩阵（Kinship Matrix）来捕捉多基因背景。
    *   **算法实现**：基于 RAINBOWR 算法优化权重，并利用 `rNeighborGWAS` 软件包进行实现。

### 3. 实验设计
*   **数据集/场景**：
    1.  **基准模拟（Benchmark Simulation）**：利用 SLiM 软件模拟了 30 个独立基因组数据集，设定不同的 DGE-IGE 协方差（0, ±0.3, ±0.6），评估模型在参数估计、预测准确度（$R^2$）和 GWAS 效能（AUC）上的表现。
    2.  **真实数据集应用**：
        *   **颤杨（Aspen）**：WisAsp 项目数据，包含 18 个性状。
        *   **苹果（Apple）**：REFPOP 项目数据，跨欧洲 6 个地点、30 个性状。
        *   **葡萄（Grape）**：INNOVINE 项目数据，19 个性状。
*   **对比方法**：主要对比了**包含协方差参数的模型（cov）**与**不包含协方差参数的传统模型（noncov）**。

### 4. 资源与算力
*   **算力说明**：文中提到计算资源由东京大学医科学研究所的人类基因组中心（Human Genome Center）提供（Shirokane 超级计算机）。
*   **具体细节**：论文未明确说明具体的 GPU/CPU 型号、数量或具体的训练时长。

### 5. 实验数量与充分性
*   **实验规模**：
    *   模拟实验进行了 30 次独立迭代，覆盖了从强负相关到强正相关的多种遗传架构场景。
    *   应用实验涵盖了三种具有不同生长习性的木本植物（乔木与攀缘植物），涉及多年、多地点的观测数据。
*   **充分性与客观性**：实验设计较为充分。通过模拟验证了模型在不同信噪比下的稳健性，并利用交叉验证（10-fold CV）评估预测能力。使用真实世界中具有空间布局记录的数据集，增强了结果的说服力和实际应用价值。

### 6. 论文的主要结论与发现
*   **模型效能**：新模型能有效推断 DGEs 和 IGEs 之间的权衡关系。在正相关场景下，包含协方差参数能显著提升基因组预测的准确性。
*   **生物学发现**：
    *   **竞争证据**：在杨树和苹果的生长性状（如树干周长增量）中发现了显著的负 DGE-IGE 协方差，证实了种内竞争的存在。
    *   **生长阶段相关性**：苹果树的竞争强度随树龄增长（树干变粗）而显著增加。
    *   **性状差异**：物候性状（如花期）主要受 DGEs 控制，而生长性状受 IGEs 影响较大。
    *   **QTL 定位**：在苹果第 7 号染色体上检测到与竞争性 IGEs 相关的显著位点，并筛选出潜在的候选基因（如蛋白激酶超家族蛋白）。

### 7. 优点
*   **理论创新**：巧妙地将物理学伊辛模型引入数量遗传学，为邻体相互作用提供了直观的数学解释。
*   **功能统一**：一个模型同时实现了 GWAS（定位主效位点）和 GP（评估全基因组贡献），提高了分析效率。
*   **空间解析力**：能够处理复杂的空间布局数据，特别适合林木、作物等无法移动的生物群体研究。

### 8. 不足与局限
*   **数值稳定性**：在 DGE-IGE 为负相关时，加权核矩阵可能不是正定的，虽然通过算法近似解决，但可能导致负协方差的估计不够稳定。
*   **计算复杂性**：多核混合模型的参数估计（尤其是 REML 过程）在大规模群体数据下计算开销较大。
*   **应用限制**：模型高度依赖准确的空间位置元数据（Metadata），若缺乏精确的邻体距离信息，模型效能将受限。
*   **物种偏差**：在攀缘植物（如葡萄）中未检测到强烈的 IGEs，说明该模型在不同生态位或生长型的物种间适用性存在差异。

（完）
