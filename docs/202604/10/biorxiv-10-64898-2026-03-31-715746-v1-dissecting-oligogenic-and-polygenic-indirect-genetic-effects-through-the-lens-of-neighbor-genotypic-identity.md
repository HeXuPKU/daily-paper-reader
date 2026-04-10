---
title: Dissecting oligogenic and polygenic indirect genetic effects through the lens of neighbor genotypic identity
title_zh: 从邻体基因型一致性视角剖析寡基因与多基因间接遗传效应
authors: "Sato, Y., Hamazaki, K."
date: 2026-04-03
pdf: "https://www.biorxiv.org/content/10.64898/2026.03.31.715746v1.full.pdf"
tags: ["query:gwas"]
score: 10.0
evidence: 针对间接遗传效应的统一GWAS和基因组预测方法
tldr: 本研究探讨了个体表型受邻居基因型影响的间接遗传效应（IGEs）。作者借鉴铁磁学伊辛模型，开发了一种整合多基因和寡基因IGEs的多核混合模型，旨在统一IGEs的基因组预测（GP）和全基因组关联分析（GWAS）。通过对杨树、苹果和葡萄等木本植物的应用，揭示了种内竞争的遗传基础，为解析群体表现的遗传结构提供了灵活且有效的工具。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-31-715746-v1/fig-001.webp\", \"caption\": \"Figures 528\", \"page\": 19, \"index\": 1, \"width\": 852, \"height\": 594}]"
motivation: 旨在解决当前缺乏统一方法来同时开展间接遗传效应（IGEs）的基因组预测和全基因组关联分析的问题。
method: 借鉴物理学伊辛模型，提出一种包含两个随机效应且使用单一协方差参数的多核混合模型来简化IGEs的计算。
result: 模拟证实该模型能有效推断直接与间接遗传效应间的权衡，并在杨树和苹果树中检测到了显著的种内竞争效应及相关遗传变异。
conclusion: 该研究提供了一个灵活的IGEs分析框架，为解析生物群体表现的遗传架构和种内互作提供了强有力的工具。
---

## 摘要
个体表型通常取决于群体内其他个体的基因型。这些现象被称为间接遗传效应（IGEs），并已通过数量遗传模型与直接遗传效应（DGEs）区分开来。近期的研究利用高分辨率多态性数据实现了 IGEs 的基因组预测（GP）和全基因组关联分析（GWAS），但统一的方法仍然有限。在本研究中，我们利用包含两个随机效应且具有单一协方差参数的多核混合模型，整合了多基因和寡基因 IGEs。在该实现的基础上，铁磁学的伊辛模型（Ising model）使我们能够分别简化用于 GWAS 和 GP 的位点级和背景 IGEs。我们的模拟表明，虽然先前模型与本模型表现出相似的性能，但本模型可以推断 DGEs 和 IGEs 之间的权衡。通过将该方法应用于三种木本植物，我们在杨树和苹果树中发现了基因型间竞争的证据，但在攀缘葡萄藤中证据有限。基于 GWAS，我们还检测到了与苹果树干生长的竞争性 IGEs 相关的显著变异位点。我们的研究为 IGEs 的 GWAS/GP 提供了一种灵活的实现方式，从而为剖析群体表现的遗传结构提供了有效的工具。

## Abstract
Individual phenotypes often depend on the genotypes of other individuals within a group. These phenomena are termed  indirect genetic effects (IGEs) and have been distinguished from direct genetic effects (DGEs) using quantitative genetic models. Recent studies have utilized high-resolution polymorphism data to enable genomic prediction (GP) and genome-wide association study (GWAS) of IGEs, but unified methods remain limited. Here we integrate polygenic and oligogenic IGEs using a multi-kernel mixed model incorporating two random effects with a single covariance parameter. Underlying this implementation, the Ising model of ferromagnetics enabled us to simplify locus-wise and background IGEs for GWAS and GP, respectively. Our simulations demonstrated that, while the previous and present models exhibited similar performance, the present model can infer a trade-off between DGEs and IGEs. By applying this method to three species of woody plants, we found evidence for intergenotypic competition in aspen and apple trees, but limited evidence in climbing grapevines. Based on GWAS, we also detected significant variants associated with the competitive IGEs on the apple trunk growth. Our study offers a flexible implementation for GWAS/GP of IGEs, thereby providing an effective tool to dissect the genetic architecture of group performance.

---

## 论文详细总结（自动生成）

这篇论文题为《从邻体基因型一致性视角剖析寡基因与多基因间接遗传效应》，由 Yasuhiro Sato 和 Kosuke Hamazaki 撰写。以下是对该论文的结构化总结：

### 1. 核心问题与整体含义（研究动机和背景）
*   **核心问题**：个体的表型不仅受自身基因型（直接遗传效应，DGEs）影响，还受群体内邻居基因型（间接遗传效应，IGEs）的影响。目前缺乏一种统一的方法，能同时对 IGEs 进行全基因组关联分析（GWAS，针对主效/寡基因）和基因组预测（GP，针对微效/多基因）。
*   **研究背景**：在植物和动物育种中，理解 IGEs 对于优化群体表现（如减轻种内竞争）至关重要。然而，识别导致 IGEs 的中间性状非常困难，因此需要基于基因型的直接建模。

### 2. 方法论：核心思想与关键技术
*   **核心思想**：借鉴物理学中描述铁磁性的**伊辛模型（Ising model）**，将邻居间的基因型相互作用类比为磁偶极子间的物理相互作用。
*   **关键技术细节**：
    *   **多核混合模型**：利用 RAINBOW 算法框架，构建了一个包含两个随机效应（DGE 和 IGE）的线性混合模型。
    *   **模型公式化**：模型将表型分解为固定效应（用于 GWAS 的单位点 DGE、IGE 及其交互项）和随机效应（用于 GP 的多基因背景效应）。
    *   **协方差参数 ($\rho_{12}$)**：引入了一个关键的协方差参数，用于衡量 DGE 和 IGE 之间的相关性。这可以揭示个体表现与群体贡献之间的遗传权衡（如竞争或协作）。
    *   **空间加权**：通过邻体基因型一致性矩阵（Kinship matrix）来捕捉空间遗传结构，纠正群体分层带来的假阳性。

### 3. 实验设计
*   **数据集/场景**：
    *   **模拟数据**：基于 SLiM 软件生成的 30 组独立基因组数据，设置了不同的 DGE-IGE 协方差水平（0, ±0.3, ±0.6）。
    *   **真实数据**：应用三种木本植物数据集：颤杨（WisAsp 项目，18 个性状）、苹果（REFPOP 项目，30 个性状，跨欧洲 6 个站点）和葡萄（INNOVINE 项目，19 个性状）。
*   **Benchmark 与对比**：
    *   对比了包含协方差参数（cov）与不包含该参数（noncov）的模型性能。
    *   评估指标包括预测准确性（$R^2$）、平均绝对误差（MAE）、GWAS 的检出能力（AUC 和灵敏度）。

### 4. 资源与算力
*   **算力说明**：论文提到计算资源由东京大学医科学研究所的人类基因组中心（Shirokane 超算）提供。
*   **细节缺失**：文中未明确列出具体的 GPU/CPU 型号、核心数量或具体的训练/运行总时长。

### 5. 实验数量与充分性
*   **实验规模**：
    *   模拟实验进行了 30 次独立迭代，覆盖了正向、负向和零协方差多种情景。
    *   真实数据涵盖了多年份、多地点的观测，样本量从数百到数万个体不等。
*   **充分性评价**：实验设计较为充分且客观。通过模拟验证了模型在不同遗传架构下的稳健性，并通过跨物种的应用证明了模型的普适性。

### 6. 主要结论与发现
*   **模型效能**：新模型在 GP 预测中，当 DGE 和 IGE 呈正相关时表现更优；在 GWAS 中，无论协方差如何，均能有效检测到致病位点。
*   **生物学发现**：
    *   **种内竞争**：在杨树和苹果的生长性状（如树干周长增量）中发现了显著的负遗传协方差，表明存在强烈的种内竞争，且这种竞争随树木成熟而加剧。
    *   **物种差异**：攀缘植物（葡萄）中未发现明显的竞争性 IGEs，可能与其垂直生长模式和光响应可塑性有关。
    *   **位点识别**：在苹果中识别出两个与树干生长竞争相关的显著 IGE 变异位点，位于 7 号染色体，涉及蛋白激酶相关基因。

### 7. 优点
*   **统一框架**：首次将 IGEs 的 GWAS 和 GP 整合进一个灵活的多核混合模型中。
*   **物理学跨界应用**：引入伊辛模型为理解复杂的生物社会相互作用提供了直观的数学解释。
*   **实用性**：提供了开源 R 软件包（`rNeighborLMM`），便于其他研究者应用。

### 8. 不足与局限
*   **数值稳定性**：当协方差为负时，模型估计的变异性较大，且可能导致核矩阵非正定，需要进行近似处理，这可能影响预测精度。
*   **空间数据依赖**：模型高度依赖精确的个体空间位置元数据，若缺乏空间信息则无法应用。
*   **计算复杂性**：多核混合模型的参数优化（尤其是权重分配）比传统单核模型更耗时。

（完）
